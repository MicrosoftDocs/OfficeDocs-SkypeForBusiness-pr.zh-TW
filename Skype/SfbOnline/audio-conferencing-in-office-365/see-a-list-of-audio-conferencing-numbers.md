---
title: 在商務用 Skype Online 中查看音訊會議號碼清單
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: '瞭解如何在商務用 Skype Online 中尋找電話撥入式會議號碼。 '
ms.openlocfilehash: f7343010cfdc34325d2f164b5560c542af0551ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114149"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>在商務用 Skype Online 中查看音訊會議號碼清單

> [!NOTE]
> 有關 Microsoft Teams 中音訊會議號碼的資訊，請參閱在 Microsoft Teams 中查看音訊 [會議號碼清單](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)。

當您為商務用 Skype 使用者設定音訊會議時，您可以查看他們可用於音訊會議的電話號碼。 此清單會包含貴組織可用的所有音訊會議電話號碼。
  
 **想要尋找價格嗎？** 請參閱 [音訊會議的價格](https://products.office.com/skype-for-business/audio-conferencing#Requirements)。
  
> [!IMPORTANT]
> **沒有任何資源會包含音訊會議的所有撥入號碼清單。** 如果您想要查看您的地區或國家/地區是否有可用的撥入電話號碼，請前往商務用 **Skype** 系統管理中心語音電話號碼，按一下 [新增，然後按一下 [新增  >    >  ******服務號碼**> 。  使用 [國家/地區]、[州/地區] 和 [城市] 的清單來篩選搜尋。 此外，如果您要尋找免付費服務號碼， **請從州** /地區清單中選取免 **付費** 。
  
如果貴組織中只有一個電話號碼可用，它會做為所有使用者的預設號碼。 當有多個電話號碼可用時，您可以選取每個使用者的預設電話號碼。 此預設號碼會包含在商務用 Skype 會議邀請中。
  
您可以看見設定 [邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md) ，以變更單一使用者的撥入電話號碼。
  
> [!NOTE]
> 國內撥入號碼是貴組織專用的號碼，是唯一可以設定為預設電話號碼的號碼。 不過，國際撥入號碼可能會跨多個組織共用。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>若要查看您的音訊會議電話號碼

1. 使用公司或學校帳戶來登錄。
    
2. 前往商務用 Skype > **系統管理中心**。
    
3. 在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **Microsoft 橋接器**，然後：
    
   - 您可以查看音訊會議可用的電話號碼。
    
   - 您也可以查看位置，以及音訊會議自動語音機將會使用的主要和次要語言。
    
> [!NOTE]
> 您可以前往音訊 **會議** 使用者，然後選取使用者的屬性，從貴組織中可用號碼清單中選擇新號碼，以  >  變更預設號碼。 請參閱 [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動化這項功能，您可以使用 [Get-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber) Cmdlet。
    
- Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
