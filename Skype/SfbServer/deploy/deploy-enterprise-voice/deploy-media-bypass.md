---
title: 在商務用 Skype Server 中部署媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: 在商務用 Skype Server Enterprise Voice 中部署媒體旁路。 包括先決條件和部署程式檢查清單。
ms.openlocfilehash: 2cbb57499a4cdb38a83424b3c86445817b18b4c5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233513"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>在商務用 Skype Server 中部署媒體旁路
 
在商務用 Skype Server Enterprise Voice 中部署媒體旁路。 包括先決條件和部署程式檢查清單。
  
本主題假設您已經發佈並設定至少一或多個中繼伺服器, 以及至少一個閘道對等來提供 PSTN 連線。 如需這些工作的詳細資訊, 請參閱在商務用 Skype Server 的 [拓撲建立器] 中[部署轉送伺服器](deploy-a-mediation-server.md), 並在商務用 skype server 的 [拓撲建立器] 中[定義閘道](define-a-gateway.md)。
  
 如果您所連線的對等是 SIP 中繼提供者的 SBC, 請確認提供者是合格的提供者, 且提供者支援媒體旁路。 例如, 許多 SIP 中繼提供者將只允許其 SBC 接收來自中繼伺服器的流量。 如果是, 則不能針對有問題的主幹啟用旁路。 此外, 除非您的組織向 SIP 中繼提供者顯示其內部網路 IP 位址, 否則您無法啟用媒體旁路。
  
> [!NOTE]
> 媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道, 並有已認證的合作夥伴, 且已使用 Cisco IP-Pbx 進行了一些測試。 只有在[整合通訊開啟互通性程式 (Lync Server)](https://go.microsoft.com/fwlink/p/?linkId=214406)中列出的產品與版本支援媒體略過。 
  
如果您已經有選擇設定 [呼叫許可控制 (CAC)], 另一個高級企業語音功能, 請注意, 通話許可控制所執行的頻寬保留不會套用到任何已使用媒體略過的呼叫。 驗證是否會先執行媒體略過, 如果是採用媒體旁路, 通話許可控制則不會用於通話;只有在媒體旁路檢查失敗時, 才會執行 [通話許可控制] 的檢查。 因此, 對於路由至 PSTN 的任何特定呼叫, 這兩項功能都是互斥的。 這是因為媒體旁路假設在通話中的媒體端點之間不存在頻寬限制;無法在頻寬限制的連結上執行媒體旁路。 因此, 下列其中一項將會套用至 PSTN 通話: a) 媒體繞過中繼伺服器, 且通話許可控制不會保留通話的頻寬;or b) 通話許可控制將頻寬保留套用至通話, 而媒體則由通話中所涉及的中繼伺服器來處理。
  
除了為與對等相關聯的個別幹線連線啟用媒體旁路之外, 您還必須啟用全域旁路媒體。 全域媒體旁路設定可以指定媒體略過嘗試撥打電話給 PSTN, 或者使用子網至網路網站和網路區域的對應, 就像是由通話許可控制所做的一樣, 另一個[高級語音] 功能。 當 [媒體旁路] 和 [呼叫許可控制] 都已啟用時, 系統會在判斷是否要使用媒體旁路時, 自動使用為 [呼叫許可控制] 所指定的網路區域、網路網站及子網資訊。 這表示您無法指定在已啟用呼叫許可控制的情況下, 不會針對 PSTN 呼叫總是嘗試使用媒體旁路。
  
> [!NOTE]
> 當您使用這些步驟來設定媒體旁路時, 假設您在用戶端與中繼伺服器對等 (例如 PSTN 閘道、IP PBX 或 SIP 中繼提供者的 SBC) 之間有良好的連線能力。 如果連結有任何頻寬限制, 則無法將媒體略過套用至通話。 媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道, 並有已認證的合作夥伴, 且已使用 Cisco IP-Pbx 進行了一些測試。 只有在[整合通訊開啟互通性程式 (Lync Server)](https://go.microsoft.com/fwlink/p/?linkId=214406)中列出的產品與版本支援媒體略過。 
  
## <a name="deployment-process-for-media-bypass"></a>媒體略過的部署程式

下表提供媒體旁路部署程式的概覽。 
  
|**分**|**步驟**|**角色**|**部署檔**|
|:-----|:-----|:-----|:-----|
|針對媒體旁路設定 trunks  <br/> |如果您尚未這麼做, 請針對媒體旁路設定一或多個 trunks。  <br/> | RTCUniversalServerAdmins 群組的成員, 或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員 <br/> |[在商務用 Skype Server 中使用 [旁路媒體] 設定主幹](configure-trunk-with-media-bypass.md) <br/> |
|將媒體設定為全域略過  <br/> |針對所有的 PSTN 呼叫設定媒體旁路, 或根據網路網站和網路區域進行特定的呼叫。  <br/> | RTCUniversalServerAdmins 群組的成員, 或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員 <br/> |[在商務用 Skype Server 中設定媒體旁路, 以永遠略過中繼伺服器](bypass-the-mediation-server.md) <br/> [在商務用 Skype Server 中設定媒體旁路全域設定以使用網站和區域資訊](use-site-and-region-information.md) <br/> |
|如有需要, 將子網與網路網站建立關聯  <br/> |如果您將 [旁路媒體] 設定為使用網站和區域資訊, 則必須將您的部署子網與網路網站和區域建立關聯 (如果您尚未這麼做, 其他語音功能也一樣)。  <br/> | RTCUniversalServerAdmins 群組的成員, 或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員 <br/> |[建立子網路與網路站台的關聯](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

