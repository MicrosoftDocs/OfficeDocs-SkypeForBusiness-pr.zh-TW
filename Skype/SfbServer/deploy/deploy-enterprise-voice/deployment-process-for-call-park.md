---
title: 商務用 Skype 中通話駐留的部署程式
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 商務用 Skype Server 企業語音中通話駐留的部署程式與步驟。
ms.openlocfilehash: bfc6a2455ba010f05083872ee8c394244ef4827b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393385"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>商務用 Skype 中通話駐留的部署程式
 
商務用 Skype Server 企業語音中通話駐留的部署程式與步驟。
  
通話駐留可讓企業語音使用者將來電保留在一部電話中，然後再撥打 (（稱為通話駐留軌道) 從任何電話）的內部號碼來取回通話。
  
當您部署企業語音時，會自動在前端伺服器或 Standard Edition Server 上安裝及啟用呼叫駐留所使用的元件。 不過，您必須使用下列步驟來設定通話駐留，使用者才能使用它。 
  
**通話駐留部署程式**

|**階段**|**步驟**|**所需群組和角色**|**部署文件**|
|:-----|:-----|:-----|:-----|
|在軌道表格中設定通話駐留軌道範圍  <br/> |使用商務用 Skype Server 控制台或 **New-CSCallParkOrbit** 指令程式，建立通話駐留軌道表格中的軌道範圍，並將它們與主控通話駐留應用程式的應用程式服務建立關聯。 <br/> **注意：** 為了與現有的撥號對應表進行無縫整合，軌道範圍通常會設定為虛擬擴充區塊。 指派直接向內撥號 (，不支援通話駐留軌道表格中的軌道編號) 數位。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中建立或修改通話駐留軌道範圍](create-or-modify-a-call-park-orbit-range.md) <br/> |
|設定通話駐留設定  <br/> | 使用 **Set-CsCpsConfiguration** Cmdlet 來設定通話駐留設定。 建議您至少將 **OnTimeoutURI** 選項設定為設定要在寄存通話超時時使用的回退目的地。您也可以設定下列設定： <br/>   (選用) **EnableMusicOnHold** 啟用或停用等候的音樂。 <br/>   (選用) **MaxCallPickupAttempts** 決定寄存來電在將來電轉送至回復的備用資源識別元 (URI) 之前所用的次數。 <br/>   (選用) **CallPickupTimeoutThreshold** 可決定通話之後所經過的時間長度，超過此時間之後，它會在接聽來電的電話之前所經過的時間。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[設定商務用 Skype 中的通話駐留設定](configure-call-park-settings.md) <br/> |
|（選用）自訂等候音樂  <br/> |如果您不想要使用預設的等候音樂，請使用 **Set-CsCallParkServiceMusicOnHoldFile** Cmdlet 自訂和上傳音訊檔案。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[自訂通話駐留 inSkype for Business 的等候音樂](customize-call-park-music-on-hold.md) <br/> |
|設定語音原則為使用者啟用通話駐留  <br/> |使用 **EnableCallPark** 選項來商務用 Skype Server 控制台或 **Set-CSVoicePolicy** 指令程式，以在語音原則中為使用者啟用通話駐留。 <br/> 預設會停用所有使用者的通話駐留。  <br/> 如果您有多個語音原則，請確定針對每個語音原則設定 EnableCallPark 屬性，而不只是針對預設原則。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[為商務用 Skype 中的使用者啟用通話駐留](enable-call-park-for-users.md) <br/> |
|驗證通話駐留的正規化規則  <br/> |通話駐留軌道不得正規化。 請確認您的正規化規則不包含任何軌道範圍。 如有必要，請建立其他正規化規則，以防止軌道正規化。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中驗證通話駐留的正規化規則](verify-normalization-rules-for-call-park.md) <br/> |
|驗證通話駐留部署  <br/> |測試停車場和取回通話，以確保您的設定如預期般運作。  <br/> |-  <br/> |[ (選用) 在商務用 Skype 中驗證通話駐留部署](optional-verify-call-park-deployment.md) <br/> |
   

