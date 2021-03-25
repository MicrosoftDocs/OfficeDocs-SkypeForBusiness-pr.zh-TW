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
ms.openlocfilehash: 13c493e16e5a6fef8b93b80d2a0e706f8f222ffa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111959"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>音訊會議的疑難排解與已知問題

 **本文適用于使用 Microsoft 作為音訊會議提供者的商務用 Skype 使用者。不適用於使用協力廠商音訊會議提供者 (ACP) 。**
  
## <a name="troubleshooting-and-known-issues"></a>疑難排解和已知問題

使用 Microsoft 做為音訊會議提供者的音訊會議目前發生正在追蹤並積極調查的問題，且功能在未來 Microsoft 365 版本中更新時，可能會獲得解決。
  
目前，當您針對在組織中使用商務用 Skype 的人員進行音訊會議設定及使用時的潛在問題進行疑難排解時，請使用此功能做為參考。

|**問題**|**行為/徵狀**|**已知的因應措施**|**發現日期**|
|:-----|:-----|:-----|:-----|
|進入和離開通知在會議開始時會開啟，但在會議開始後會關閉。  <br/> |根據預設，參與者從商務用 Skype 應用程式加入的會議，以及參與者撥入時，進入和離開通知會停用。 您可以在商務用 Skype 應用程式中的 **Skype 會議選項** 中啟用公告。 對於所有參與者撥入並加入會議的會議，系統預設會啟用進入和離開通知，因為參與者名冊無法供任何參與者使用。 當只有參與者來電的會議開始時，進入和離開通知會開啟，但當參與者使用商務用 Skype App 加入時，通知會關閉。 關閉時，可以使用商務用 Skype 應用程式中的 **Skype 會議選項** 重新啟用通知。 <br/> |無因應措施。  <br/> |8/30/2017  <br/> |
|如果使用者第一次被指派 E5 授權來進行配置，如果信箱未啟用，音訊會議歡迎電子郵件可能不會傳送給使用者。  <br/> |如果發生這種情況，您隨時都可以在商務用 Skype 系統管理中心使用音訊會議，或使用 PowerShell 重新發送使用者的音訊會議資訊。 請參閱 [在音訊會議設定變更時啟用或停用傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注意：** 若要將音訊會議 PIN 重新發回給使用者，PIN 必須重設。 您也可以在商務用 Skype系統管理中心使用音訊會議，或使用 PowerShell 來完成這項操作。          |無因應措施。  <br/> |8/30/2017  <br/> |
|音訊會議通話最多可能需要 24 小時才能顯示在使用方式報告中。  <br/> |我們期待在未來服務更新中對此領域進行改良。  <br/> |無因應措施。  <br/> |8/30/2017  <br/> |
|當會議被商務用 Skype 使用者鎖定後，來電者撥入會議橋接器時，商務用 Skype App 中沒有任何通知指出使用者正在等待大廳。  <br/> |這項功能目前是由設計所設計，但我們已針對在未來服務更新中支援這項功能提供意見。  <br/> |無因應措施。  <br/> |8/30/2017  <br/> |
|商務用 Skype Server () 使用者于 2019 年 3 月 1 日之前指派音訊會議授權，可能無法在會議邀請中看見撥入座標。  <br/> |直到該日期，才支援為 Teams 音訊會議部署商務用 Skype Server 使用者。 它現在受到支援，是會議 [第一個的一個元件](/microsoftteams/meetings-first)。 使用者必須擁有 Teams 授權。  <br/> |需要重新啟用資源調配管道。 移除使用者的音訊會議授權、等候幾個小時，然後重新指派授權。  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)