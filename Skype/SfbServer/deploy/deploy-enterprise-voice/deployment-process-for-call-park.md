---
title: 商務用 Skype 中通話駐留的部署程式
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
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 商務用 Skype Server Enterprise Voice 中的通話駐留部署程式和步驟。
ms.openlocfilehash: 972a8cec2794afeebc0f5ab65d89291e78b7211e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191338"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>商務用 Skype 中通話駐留的部署程式
 
商務用 Skype Server Enterprise Voice 中的通話駐留部署程式和步驟。
  
[通話寄存] 可讓企業語音使用者從一部電話撥打電話, 然後從任何電話撥出內部號碼 (稱為 [通話駐留] 軌道), 稍後再取回通話。
  
當您部署企業語音時, 會在前端伺服器或標準版伺服器上自動安裝和啟用通話駐留使用的元件。 不過, 您必須先使用下列步驟來設定電話寄存, 才能供使用者使用。 
  
**通話駐留部署程式**

|**分**|**步驟**|**必要的群組和角色**|**部署檔**|
|:-----|:-----|:-----|:-----|
|設定 [軌道] 表格中的 [通話駐留軌道] 範圍  <br/> |使用商務用 Skype Server 的 [控制台] 或 [ **CSCallParkOrbit** ] Cmdlet, 在 [通話駐留軌道] 表格中建立軌道範圍, 並將它們與託管通話駐留應用程式的應用程式服務建立關聯。 <br/> **注意:** 若要與現有的撥號方案進行無縫整合, 軌道範圍通常是設定為虛擬延伸的區塊。 在 [通話駐留軌道] 表格中, 將直向內撥 (所做的) 號碼指派為軌道編號, 不受支援。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中建立或修改通話寄存軌道的範圍](create-or-modify-a-call-park-orbit-range.md) <br/> |
|設定通話寄存設定  <br/> | 使用**CsCpsConfiguration** Cmdlet 來設定 [通話駐留] 設定。 我們建議您至少設定**OnTimeoutURI**選項, 以設定在寄存通話超時時要使用的備用目的地。您也可以設定下列設定: <br/>  可選**EnableMusicOnHold**以啟用或停用音樂保留。 <br/>  可選**MaxCallPickupAttempts** , 決定在將來電轉接到回退統一資源識別項 (URI) 之前, 寄存通話響鈴回到接聽電話的次數。 <br/>  可選**CallPickupTimeoutThreshold** , 決定通話在撥出到接聽通話的電話之前所經過的時間長度。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中設定通話寄存設定](configure-call-park-settings.md) <br/> |
|或者, 您也可以自訂 [等候音樂]  <br/> |如果您不想使用預設的音樂保留, 請使用**CsCallParkServiceMusicOnHoldFile** Cmdlet 來自訂及上傳音訊檔案。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 inSkype 上自訂通話寄存音樂](customize-call-park-music-on-hold.md) <br/> |
|設定語音原則, 為使用者啟用通話駐留  <br/> |使用商務用 Skype Server 的 [控制台] 或**CSVoicePolicy** Cmdlet 搭配**EnableCallPark**選項, 即可在語音原則中為使用者啟用通話駐留。 <br/> 根據預設, 會停用所有使用者的 [通話駐留]。  <br/> 如果您有多個語音原則, 請務必針對每個語音原則設定 EnableCallPark 屬性, 而不只是針對預設原則。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中啟用電話寄存給使用者](enable-call-park-for-users.md) <br/> |
|驗證通話駐留的正規化規則  <br/> |通話駐留軌道式一定不能正常化。 確認您的正常化規則不包含任何您的軌道範圍。 如有需要, 請建立其他正常化規則, 以避免讓軌道式成為正常化的。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中驗證通話寄存的正常化規則](verify-normalization-rules-for-call-park.md) <br/> |
|確認您的電話寄存部署  <br/> |測試停用和檢索通話, 以確保您的設定如預期的那樣正常運作。  <br/> |-  <br/> |[可選在商務用 Skype 中確認通話駐留部署](optional-verify-call-park-deployment.md) <br/> |
   

