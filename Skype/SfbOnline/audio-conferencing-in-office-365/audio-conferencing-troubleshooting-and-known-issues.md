---
title: 音訊會議疑難排解和已知問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '當您使用 Microsoft 作為電話撥入式會議提供者、狀態及一些因應措施時，請取得已知問題的清單。 '
ms.openlocfilehash: bfb76c23d3b1235bf67435e0af09ddef2a8852f3
ms.sourcegitcommit: bb8577aca8c7e0673b37634a24bf793c86c0537b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2019
ms.locfileid: "37642913"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>音訊會議疑難排解和已知問題

 **本文適用于使用 Microsoft 作為音訊會議提供者的商務用 Skype 使用者。不適用於使用協力廠商音訊會議提供者（ACP）的客戶。**
  
## <a name="troubleshooting-and-known-issues"></a>疑難排解及已知問題

使用 Microsoft 作為音訊會議提供者的音訊會議有目前正在追蹤和積極調查的問題，而且在未來版本的 Office 365 更新此功能時可能會解決這個問題。
  
現在，當您要針對在您的組織中使用商務用 Skype 進行語音會議設定及使用的人員時，請使用此方法做為參考。

|**出現**|**行為/症狀**|**已知的解決方法**|**探索日期**|
|:-----|:-----|:-----|:-----|
|進入和結束通知會在會議開始時開啟，但在會議開始之後不久就會關閉。  <br/> |根據預設，在參與者從商務用 Skype 應用程式和撥入時加入的會議中，會停用進入與結束通知。 您可以在商務用 Skype 應用程式的**Skype 會議選項**中啟用宣告。 對於所有參與者都撥入並加入會議的會議，預設會啟用 [進入與結束通知]，因為參與者名單不提供給任何參與者。 當會議開始時只有參與者撥入，進入和結束通知就會開啟，但當參與者加入使用商務用 Skype app 時，通知就會關閉。 關閉之後，就可以使用商務用 Skype 應用程式中的**Skype 會議選項**來重新啟用通知。 <br/> |沒有解決方法。  <br/> |8/30/2017  <br/> |
|如果使用者是以指派 E5 授權的方式第一次進行設定，則在未啟用信箱的情況下，不會將音訊會議歡迎電子郵件傳送給使用者。  <br/> |如果發生這種情況，您可以在商務用 Skype 系統管理中心或使用 PowerShell 中，隨時使用**音訊會議**重新傳送使用者的音訊會議資訊。 請參閱[啟用或停用音訊會議設定變更時的傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注意：** 若要將音訊會議 PIN 重新傳送給使用者，必須重設 PIN。 您也可以在商務用 Skype 系統管理中心或使用 PowerShell 中使用**音訊會議**來完成此動作。          |沒有解決方法。  <br/> |8/30/2017  <br/> |
|音訊會議通話可能需要長達24小時才能顯示在使用狀況報告中。  <br/> |我們正期待在未來的服務更新中改善這個領域。  <br/> |沒有解決方法。  <br/> |8/30/2017  <br/> |
|當來電者在會議被商務用 Skype 使用者鎖定之後，當來電者撥入會議橋接器時，商務用 Skype 應用程式中沒有通知，指出使用者正在大廳等候。  <br/> |這是目前的設計，但我們已取得在未來服務更新中支援此功能的意見反應。  <br/> |沒有解決方法。  <br/> |8/30/2017  <br/> |
|在2019年3月1日之前指派音訊會議授權的商務用 Skype 伺服器（內部部署）使用者，在會議邀請中可能看不到撥入座標。  <br/> |在該日期之前，不支援針對團隊的商務用 Skype Server 使用者提供音訊會議。 它現在受到支援，且是[會議](https://docs.microsoft.com/microsoftteams/meetings-first)的元件。 使用者必須擁有團隊授權。  <br/> |必須重新啟用預配管道。 移除使用者的音訊會議授權，等待幾個小時，然後重新指派授權。  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>相關主題

[在 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
