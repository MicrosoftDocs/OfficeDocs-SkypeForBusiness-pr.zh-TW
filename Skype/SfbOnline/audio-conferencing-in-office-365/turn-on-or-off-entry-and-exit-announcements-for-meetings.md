---
title: 在商務用 Skype Online 中開啟或關閉會議進入和離開公告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: '瞭解如何使用商務用 Skype 系統管理中心在商務用 Skype Online 會議開啟或關閉進入和離開公告。 '
ms.openlocfilehash: 5165facfdc4de040b24b199cd99a1bb42565a76b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111929"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>在商務用 Skype Online 中開啟或關閉會議進入和離開公告

> [!Note]
> 有關 Microsoft Teams 中的進入和退出公告的資訊，請參閱開啟或關閉 Microsoft Teams 會議進入 [或退出公告](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)。

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，會取得音訊會議橋接器。 會議橋接器可以包含一或多個電話號碼，供人員用於撥打商務用 Skype 會議。 
  
會議橋接器會針對使用電話撥入會議的使用者接聽電話。 會議橋接器會從會議自動語音應答接聽來電者語音提示，然後視您的設定播放通知、要求來電者錄製其名稱，以及設定 PIN 安全性。 PIN 會提供給商務用 Skype 會議召集人，而且如果他們無法使用商務用 Skype 應用程式開始會議，就可以開始會議。 不過，您可以將其設定為不需要 PIN 才能開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>設定會議加入選項
    
1. 在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **Microsoft 橋接器設定**。
    
2. 在 **會議加入體驗下**，選取或清除啟用會議進入和離開 **通知以開啟**。 這是預設選取的。 如果您清除，當某人進入或離開會議時，已加入會議的使用者不會收到通知。
    
3. 在 **進入/離開公告類型下**，選取名稱 **或電話號碼** 或 **語音**。
    
4. 檢查或取消勾選 **要求來電者在加入會議前先錄製他們的名稱**。
    
5. 進行變更後，按一下 [**儲存。**
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet。
    
- 在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次變更許多使用者的設定時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[音訊會議的常見問題](/MicrosoftTeams/audio-conferencing-common-questions)