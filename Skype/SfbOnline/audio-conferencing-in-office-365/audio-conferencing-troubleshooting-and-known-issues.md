---
title: 音訊會議的疑難排解與已知問題
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '取得使用 Microsoft 作為電話撥入式會議提供者時已知問題的清單、狀態，以及一些因應措施。 '
ms.openlocfilehash: 71d363ff98fc4590fb6d96cc3e8a8cb77b1fa24c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237189"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>音訊會議的疑難排解與已知問題

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 **本文適用于使用 microsoft 商務用 Skype音訊會議提供者的使用者。它不適用於使用協力廠商音訊會議提供者 (ACP) 。**
  
## <a name="troubleshooting-and-known-issues"></a>疑難排解和已知問題

使用 Microsoft 做為音訊會議提供者的音訊會議目前發生正在追蹤並積極調查的問題，且日後更新功能後，Microsoft 365。
  
目前，當您針對在組織中使用音訊會議進行音訊會議設定及商務用 Skype疑難排解時，請使用此功能做為參考。

|**問題**|**行為/徵狀**|**已知的因應措施**|**發現日期**|
|:-----|:-----|:-----|:-----|
|進入和離開通知在會議開始時會開啟，但在會議開始後會關閉。  <br/> |根據預設，參與者從兩個應用程式加入的會議，以及參與者撥入時，商務用 Skype和離開通知會停用。 您可以在應用程式Skype會議選項中 **啟用** 商務用 Skype公告。 對於所有參與者撥入並加入會議的會議，系統預設會啟用進入和離開通知，因為參與者名冊無法供任何參與者使用。 當只有參與者來電的會議開始時，進入和離開通知會開啟，但當參與者使用 商務用 Skype 應用程式加入時，通知會關閉。 關閉時，您可以在應用程式 **Skype會議選項** 商務用 Skype通知。 <br/> |無因應措施。  <br/> |8/30/2017  <br/> |
|如果使用者第一次被指派 E5 授權來進行配置，如果信箱未啟用，音訊會議歡迎電子郵件可能不會傳送給使用者。  <br/> |如果發生這種情況，您隨時都可以使用系統管理中心的音訊會議，或使用 PowerShell重新商務用 Skype音訊會議資訊。 請參閱 [在音訊會議設定變更時啟用或停用傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注意：** 若要將音訊會議 PIN 重新發回給使用者，PIN 必須重設。 您也可以在系統管理中心使用音訊商務用 Skype或 PowerShell。          |無因應措施。  <br/> |8/30/2017  <br/> |
|音訊會議通話最多可能需要 24 小時才能顯示在使用方式報告中。  <br/> |我們期待在未來服務更新中對此領域進行改良。  <br/> |無因應措施。  <br/> |8/30/2017  <br/> |
|當來電者在會議被 商務用 Skype 使用者鎖定後撥入會議橋接器時，商務用 Skype 應用程式中沒有通知指出使用者正在等待大廳。  <br/> |這項功能目前是由設計所設計，但我們已針對在未來服務更新中支援這項功能提供意見。  <br/> |無因應措施。  <br/> |8/30/2017  <br/> |
|商務用 Skype Server (2019) 3 月 1 日之前指派音訊會議授權的使用者，可能無法在會議邀請中看到撥入座標。  <br/> |直到商務用 Skype Server，Teams音訊會議的使用者才受支援。 現在支援它，且是會議 [第一部分](/microsoftteams/meetings-first)。 使用者必須擁有Teams授權。  <br/> |需要重新啟用資源調配管道。 移除使用者的音訊會議授權、等候幾個小時，然後重新指派授權。  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
