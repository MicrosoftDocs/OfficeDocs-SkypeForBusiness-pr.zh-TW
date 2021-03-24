---
title: 在商務用 Skype Server 中部署媒體旁路
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: 在商務用 Skype Server Enterprise Voice 中部署媒體旁路。 包含必要條件和部署程式檢查清單。
ms.openlocfilehash: be29d86dc9e7bd627a83b41d4666eacfcb6d46a4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097079"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>在商務用 Skype Server 中部署媒體旁路
 
在商務用 Skype Server Enterprise Voice 中部署媒體旁路。 包含必要條件和部署程式檢查清單。
  
本主題假設您已發佈和設定至少一或多部轉送伺服器，以及至少一個閘道對等以提供 PSTN 連線能力。 如需這些工作的詳細資訊，請參閱在商務用 [Skype server 的拓撲](deploy-a-mediation-server.md) 產生器中部署轉送伺服器，並 [在商務用 Skype server 的拓撲產生器中定義閘道](define-a-gateway.md)。
  
 如果您所連接的對等是 SIP 主幹提供者的 SBC，請確定提供者是合格的提供者，而且提供者支援媒體旁路。 例如，許多 SIP 主幹提供者只會允許其 SBC 從轉送伺服器接收流量。 如果是的話，則不能針對有問題的主幹啟用旁路。 此外，除非您的組織對 SIP 主幹提供者顯示其內部網路 IP 位址，否則您無法啟用媒體旁路。
  
> [!NOTE]
> 媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。 Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。 只有在 [整合通訊開啟互通性計畫-Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)上列出的產品及版本，才支援媒體旁路。 
  
如果您已選擇性設定通話許可控制 (CAC) ，另一種高級 Enterprise Voice 功能，請注意，「通話許可控制」所執行的頻寬保留不會套用到使用媒體旁路的任何呼叫。 驗證是否要使用媒體旁路，以及是否採用媒體旁路，通話許可控制不會用於通話;只有在媒體旁路檢查失敗時，才會為通話許可控制執行支票。 針對路由傳送至 PSTN 的任何特殊呼叫，這兩種功能都是互斥的。 這是因為媒體旁路假設在通話上的媒體端點之間不存在頻寬限制，所以此邏輯為此邏輯。媒體旁路無法在限制頻寬的連結上執行。 因此，下列其中一項會套用至 PSTN 通話：) 媒體略過轉送伺服器，而通話許可控制並未保留通話的頻寬;or b) 通話許可控制會將頻寬保留套用至通話，並由通話所涉及的轉送伺服器處理媒體。
  
除了啟用對等端相關之個別主幹連線的媒體旁路，您也必須通用啟用媒體旁路。 通用媒體旁路設定可以指定媒體旁路對 PSTN 的呼叫永遠嘗試，或使用子網對應至網路網站和網路地區（類似于通話許可控制，另一種高級語音功能）來使用媒體旁路。 當 media 旁路和通話許可控制皆已啟用時，系統會自動使用為通話許可控制指定的網路地區、網路網站及子網資訊，以決定是否使用媒體旁路。 這表示您無法指定啟用通話許可控制時，永遠會嘗試對 PSTN 呼叫媒體旁路。
  
> [!NOTE]
> 使用下列步驟設定媒體旁路時，假設前提是用戶端和中繼伺服器對等端 (例如 PSTN 閘道、IP-PBX 或 SIP 主幹提供者上的 SBC) 之間的連線良好。 如果連結上有頻寬限制，就無法將媒體旁路套用至通話。 媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。 Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。 只有在 [整合通訊開啟互通性計畫-Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)上列出的產品及版本，才支援媒體旁路。 
  
## <a name="deployment-process-for-media-bypass"></a>媒體旁路的部署程式

下表提供媒體旁路部署程式的概述。 
  
|**階段**|**步驟**|**角色**|**部署文件**|
|:-----|:-----|:-----|:-----|
|設定媒體旁路的主幹  <br/> |若尚未設定一或多個主幹媒體旁路，請設定一或多個媒體旁路。  <br/> | RTCUniversalServerAdmins 群組的成員，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員 <br/> |[在商務用 Skype Server 中設定含媒體旁路的主幹](configure-trunk-with-media-bypass.md) <br/> |
|設定全域旁路媒體  <br/> |設定對 PSTN 所有呼叫的媒體旁路，或根據網路地點和網路地區進行的特定呼叫。  <br/> | RTCUniversalServerAdmins 群組的成員，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員 <br/> |[設定商務用 Skype Server 中的媒體旁路，以永遠略過轉送伺服器](bypass-the-mediation-server.md) <br/> [在商務用 Skype Server 中設定媒體旁路通用設定，以使用網站與地區資訊](use-site-and-region-information.md) <br/> |
|視需要將子網與網站產生關聯  <br/> |如果您將媒體旁路設定為使用網站與地區資訊，則必須將部署的子網與網路網站和區域產生關聯， (若尚未做為其他語音功能。 )   <br/> | RTCUniversalServerAdmins 群組的成員，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員 <br/> |[建立子網與網路網站的關聯](deploy-network.md#BKMK_AssociateSubnets) <br/> |
