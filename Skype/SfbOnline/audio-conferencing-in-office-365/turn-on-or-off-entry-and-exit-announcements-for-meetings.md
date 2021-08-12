---
title: 開啟或關閉線上會議參賽和商務用 Skype公告
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
description: '瞭解如何使用系統管理中心在線上商務用 Skype開啟或關閉商務用 Skype公告。 '
ms.openlocfilehash: 50f2279f309e77126cc71e922b75afe1342b09863220e4c47c32581e6b85bcc9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326969"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>開啟或關閉線上會議參賽和商務用 Skype公告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有關在 Microsoft Teams 中進入和離開公告的資訊，請參閱在 Microsoft Teams 中開啟[或關閉進入和Microsoft Teams。](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，會取得音訊會議橋接器。 會議橋接器可以包含一或多個電話號碼，使用者會使用該電話號碼商務用 Skype會議。 
  
會議橋接器會針對使用電話撥入會議的使用者接聽電話。 會議橋接器會使用來自會議自動語音應答的語音提示來接聽來電者，然後視您的設定播放通知、要求來電者錄製其名稱，以及設定 PIN 安全性。 PIN 會提供給會議商務用 Skype，如果會議召集人無法使用應用程式啟動會議，可以商務用 Skype會議。 不過，您可以將其設定為不需要 PIN 才能開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>設定會議加入選項
    
1. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。
    
2. 在 **會議加入體驗下**，選取或清除啟用會議進入和離開通知 **以開啟**。 這是預設選取的。 如果您清除，當某人進入或離開會議時，已加入會議的使用者不會收到通知。
    
3. 在 **進入/離開公告類型下**，選取名稱 **或電話號碼** 或 **語音**。
    
4. 檢查或取消勾選 **要求來電者在加入會議前先錄製他們的名稱**。
    
5. 進行變更後，按一下 [**儲存。**
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet。
    
- 當涉及Windows PowerShell商務用 Skype，商務用 Skype是管理使用者，以及允許或不允許使用者執行哪些操作。 有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell相比于僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用Windows PowerShell執行線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 模組商務用 Skype[下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[音訊會議的常見問題](/MicrosoftTeams/audio-conferencing-common-questions)
