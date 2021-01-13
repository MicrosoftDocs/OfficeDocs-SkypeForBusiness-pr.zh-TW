---
title: 在商務用 Skype Server 中部署緊急服務
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
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 在商務用 Skype Server Enterprise Voice 中部署 E9-1-1。 包含必要條件和部署程式檢查清單。
ms.openlocfilehash: 8aed5b6462ecf9d5d9fecfb0ffdc5573ca4f2352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812523"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>在商務用 Skype Server 中部署緊急服務
 
在商務用 Skype Server Enterprise Voice 中部署 E9-1-1。 包含必要條件和部署程式檢查清單。
  
增強型 9-1-1 (E9-1-1) 是緊急通知功能，可將通話方的電話號碼與市政或街道位址產生關聯。 使用這項資訊，公共安全勤務中心 (PSAP) 可以立即派遣緊急服務人員到需要幫助的來電者所在處。
  
若要支援 E9-1-1，商務用 Skype 伺服器必須能夠正確地將位置與用戶端產生關聯，並確定此資訊是用來將緊急通話路由傳送至最近的 PSAP。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署必要條件

在您部署 E9-1-1 之前，您必須已部署商務用 Skype 伺服器內部伺服器，包括中央管理存放區、前端集區或 Standard Edition Server。 您也必須部署一或多部轉送伺服器（獨立或組合前端伺服器）。 此外，E9-1-1 部署需要 SIP 主幹給合格的 E9-1-1 服務提供者或緊急位置識別號碼 (ELIN) 閘道至您公用交換電話網路 (PSTN) 。
  
## <a name="deployment-process"></a>部署程式

下表提供 E9-1-1 部署程式的概述。
  
|**階段**|**步驟**|**角色**|**部署文件**|
|:-----|:-----|:-----|:-----|
|設定語音使用方式、路由和主幹設定  <br/> |1. 建立新的 PSTN 使用方式記錄。 這與位置原則中用於 **PSTN 使用狀況** 設定的名稱相同。 <br/> 2. 建立或指派語音路由至上一個步驟中建立的 PSTN 使用方式記錄，然後將閘道屬性指向 E9-1-1 SIP 主幹或 ELIN 閘道。  <br/> 3. 若為 SIP 主幹 E9-1-1 服務提供者，請設定要使用 **Set-CsTrunkConfiguration EnablePIDFLOSupport** Cmdlet 處理 PIDF-LO 透過 SIP 進行 E9-1-1 呼叫的主幹。 <br/> 4. （選用）為 SIP 主幹 E9-1-1 服務提供者，針對未由 E9-1-1 服務提供者的 SIP 主幹處理的呼叫建立或指派本機 PSTN 路由。 如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。 如果您的 E9-1-1 服務提供者支援，請將主幹設定規則指派給將911撥號字串轉譯成直接向內撥號 (已) 國家/地區緊急通話回應中心 (ECRC) 的號碼。  <br/> |CSVoiceAdmin  <br/> |[設定商務用 Skype Server 中的 E9-1-1 語音路由](configure-an-e9-1-1-voice-route.md) <br/> |
|建立位置原則並將其指派給使用者和子網  <br/> |1. 檢查全域位置原則。  <br/> 2. 建立具有使用者層級範圍的位置原則;或者，如果組織有多個具有不同緊急用途的網站，請使用網路層級範圍建立一個位置原則。  <br/> 3. 指派位置原則給網路網站。  <br/> 4. 將適當的子網新增至網路網站。  <br/> 5. (選用) 指派位置原則給使用者原則。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (除了建立位置原則)   <br/> |[在商務用 Skype Server 中建立位置原則](create-location-policies.md) <br/> [在商務用 Skype Server 中將位置原則新增至網路網站](add-a-location-policy-to-a-network-site.md) <br/> [建立子網與網路網站的關聯](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|設定位置資料庫  <br/> |1. 使用網路元素對應至位置，填入資料庫。  <br/> 2. 針對 ELIN 閘道，將 Elin 新增至 \<CompanyName\> 該列。  <br/> 3. 設定 E9-1-1 服務提供者的連線以驗證位址。  <br/> 4. 使用 E9-1-1 服務提供者驗證位址。  <br/> 5. 發佈更新的資料庫。  <br/> 6. 若為 ELIN 閘道，請將 Elin 上傳至您的 PSTN 載體的自動位置識別 (阿裡) 資料庫。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[在商務用 Skype Server 中設定位置資料庫](configure-the-location-database.md) <br/> |
|設定高級功能 (選用)   <br/> |1. 設定 SNMP 應用程式的 URL。  <br/> 2. 設定次要位置資訊服務之位置的 URL。  <br/> |CSVoiceAdmin  <br/> |[在商務用 Skype Server 中設定 SNMP 應用程式](configure-an-snmp-application.md) <br/> [在商務用 Skype Server 中設定次要位置資訊服務](secondary-location-information-service.md) <br/> |
   

