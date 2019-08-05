---
title: 在商務用 Skype Server 中部署緊急服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 在商務用 Skype Server Enterprise Voice 中部署 E9-1-1。 包括先決條件和部署程式檢查清單。
ms.openlocfilehash: 4373797b8a96f83100a39735cf20b51558eb15d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191953"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>在商務用 Skype Server 中部署緊急服務
 
在商務用 Skype Server Enterprise Voice 中部署 E9-1-1。 包括先決條件和部署程式檢查清單。
  
增強型 9-1-1 (E9-1) 是緊急通知功能, 可將通話方的電話號碼與市政或街道位址進行關聯。 使用這項資訊, 公用安全應答點 (PSAP) 可立即在 distress 中將緊急服務傳送給來電者。
  
若要支援 E9-1, 商務用 Skype 伺服器必須能夠正確地將位置與用戶端建立關聯, 並確定此資訊是用來將緊急呼叫路由到最接近的 PSAP。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9 的部署必備元件-1-1

在您部署 E9-1-1 之前, 您必須已部署商務用 Skype Server 內部伺服器, 包括中央管理商店、前端池或標準版伺服器。 您也必須將一或多個中繼伺服器 (獨立或 collocated 與前端伺服器) 部署。 此外, E9 部署需要將 SIP 主幹轉至合格的 E9-1 服務提供者, 或緊急位置識別號碼 (ELIN) 閘道到您的公用交換電話網絡 (PSTN)。
  
## <a name="deployment-process"></a>部署程式

下表提供 E9-1-1 1 部署程式的概覽。
  
|**分**|**步驟**|**角色**|**部署檔**|
|:-----|:-----|:-----|:-----|
|設定語音使用方式、路由和主幹設定  <br/> |1. 建立新的 PSTN 使用記錄。 這與位置原則中用於**PSTN 使用**設定的名稱相同。 <br/> 2. 建立或指派語音路由至在上一個步驟中建立的 PSTN 使用記錄, 然後將閘道屬性指向 E9-1-1 SIP 幹線或 ELIN 閘道。  <br/> 3. 針對 SIP 幹線 E9-1 服務提供者, 設定將處理 E9-1-1 的主幹, 以使用**new-cstrunkconfiguration-EnablePIDFLOSupport** Cmdlet 來傳送 PIDF LO 資料。 <br/> 4. 對於 SIP 中繼 E9-1 服務提供者, 請針對未由 E9-1 服務提供者的 SIP 幹線處理的呼叫建立或指派本機 PSTN 路由。 如果無法連線至 E9-1-1 服務提供者, 就會使用這個路由。 如果您的 E9-1 服務提供者支援, 請將幹線設定規則指派給閘道, 將911撥號字串轉換為國內/地區緊急電話回應中心 (ECRC) 的直接向內撥號 (已發出) 號碼。  <br/> |CSVoiceAdmin  <br/> |[在商務用 Skype Server 中設定 E9-1-1 的語音路由](configure-an-e9-1-1-voice-route.md) <br/> |
|建立位置原則並將其指派給使用者和子網  <br/> |1. 查看全域位置原則。  <br/> 2. 使用使用者層級範圍建立位置原則;或者, 如果組織有一個以上的網站有不同的緊急用途, 請建立具有網路層級範圍的位置原則。  <br/> 3. 將位置原則指派給網路網站。  <br/> 4. 將適當的子網新增至網路網站。  <br/> 5. (選用) 將位置原則指派給使用者原則。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (建立位置原則除外)  <br/> |[在商務用 Skype Server 中建立位置原則](create-location-policies.md) <br/> [在商務用 Skype Server 中新增位置原則至網路網站](add-a-location-policy-to-a-network-site.md) <br/> [建立子網路與網路站台的關聯](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|設定位置資料庫  <br/> |1. 使用網路元素對應至位置來填入資料庫。  <br/> 2. 若要 ELIN 閘道, 請將 ELINs \<新增\>至 [公司名稱] 資料行。  <br/> 3. 設定 E9-1-1 服務提供者的連線, 以驗證位址。  <br/> 4. 使用 E9-1 服務提供者驗證位址。  <br/> 5. 發佈更新後的資料庫。  <br/> 6. 若要 ELIN 閘道, 請將 ELINs 上傳到 PSTN 載波的自動位置識別 (阿裡) 資料庫。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[在商務用 Skype Server 中設定位置資料庫](configure-the-location-database.md) <br/> |
|設定高級功能 (選用)  <br/> |1. 設定 SNMP 應用程式的 URL。  <br/> 2. 設定次要位置資訊服務之位置的 URL。  <br/> |CSVoiceAdmin  <br/> |[在商務用 Skype Server 中設定 SNMP 應用程式](configure-an-snmp-application.md) <br/> [在商務用 Skype Server 中設定次要位置資訊服務](secondary-location-information-service.md) <br/> |
   

