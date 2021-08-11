---
title: 在線上查看音訊會議號碼商務用 Skype清單
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
description: '瞭解如何在 Online 中尋找電話撥入式商務用 Skype號碼。 '
ms.openlocfilehash: 6168451038d1abf5bc73a60630e56aced355af7d58a0024aff480595c71c6c2a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310232"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>在線上查看音訊會議號碼商務用 Skype清單

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 有關音訊會議號碼Microsoft Teams，請參閱在 Microsoft Teams 中查看[音訊會議號碼Microsoft Teams。](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)

當您為商務用 Skype設定音訊會議時，您可以查看他們可用於音訊會議的電話號碼。 此清單會包含貴組織可用的所有音訊會議電話號碼。
  
 **想要尋找價格嗎？** 請參閱 [音訊會議的價格](https://products.office.com/skype-for-business/audio-conferencing#Requirements)。
  
> [!IMPORTANT]
> **沒有任何資源會包含音訊會議的所有撥入號碼清單。** 如果您想要查看您的地區或國家/地區是否有可用的撥入電話號碼，請前往 **商務用 Skype** 系統管理中心 Voice 電話 號碼，按一下 [新增，然後按一下 [新增  >    >  ******服務號碼**> 。  使用 [國家/地區]、[州/地區] 和 [城市] 的清單來篩選搜尋。 此外，如果您要尋找免付費服務號碼， **請從州** /地區清單中選取免 **付費** 。
  
如果貴組織只有一個可用的電話號碼，它會作為所有使用者的預設號碼。 當有多個電話號碼可用時，您可以選取每個使用者的預設電話號碼。 此預設號碼會包含在會議邀請商務用 Skype中。
  
您可以看見設定 [邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md) ，以變更單一使用者的撥入電話號碼。
  
> [!NOTE]
> 國內撥入號碼是貴組織專用的號碼，是唯一可以設定為預設電話號碼的號碼。 不過，國際撥入號碼可能會跨多個組織共用。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>若要查看您的音訊會議電話號碼

1. 使用公司或學校帳戶來登錄。
    
2. 請前往系統管理中心 **>商務用 Skype。**
    
3. 在 商務用 Skype **系統** 管理中心，在左側流覽中，前往 **音訊會議**  >  **Microsoft 橋接器**，然後：
    
   - 您可以查看音訊會議可用的電話號碼。
    
   - 您也可以查看位置，以及音訊會議自動語音機將會使用的主要和次要語言。
    
> [!NOTE]
> 您可以前往音訊 **會議** 使用者，然後選取使用者的屬性，從貴組織可用號碼清單中選擇新號碼，以  >  變更預設號碼。 請參閱 [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 若要節省時間或自動化這項功能，您可以使用 [Get-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber) Cmdlet。
    
- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用Windows PowerShell執行線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
