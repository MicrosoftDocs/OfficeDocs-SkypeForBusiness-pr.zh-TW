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
description: '瞭解如何在商務用 Skype Online 中查看電話撥入式會議號碼。 '
ms.openlocfilehash: 065de84b3efa5303fbf3321b0087462c23c331fe
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779409"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>在商務用 Skype Online 中查看音訊會議號碼清單

> [!NOTE]
> 如需 Microsoft 團隊中音訊會議號碼的相關資訊，請參閱[在 Microsoft 團隊中查看音訊會議號碼清單](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)。

當您設定商務用 Skype 使用者的音訊會議時，您可以查看可供音訊會議使用的電話號碼。 此清單將會包含您組織所提供的所有音訊會議電話號碼。
  
 **想要尋找價格嗎？** 請參閱[音訊會議的價格](https://products.office.com/skype-for-business/audio-conferencing#Requirements)。
  
> [!IMPORTANT]
> **沒有任何資源會包含音訊會議的所有撥入號碼清單。** 如果您想要查看您所在地區或國家/地區是否有撥入電話號碼，請移至**商務用 Skype 系統管理中心** > **語音** > **電話號碼**，按一下 [新增]，**然後按一下 [** 新的**服務號碼**]。 使用 [國家/地區]****、[州/地區]**** 和 [城市]**** 的清單來篩選搜尋。 此外，如果您正在尋找免付費服務號碼，請從 [**省/市/地區**] 清單中選取 [**免付費電話**]。
  
如果您的組織只有一個可用的電話號碼，則會將它作為所有使用者的預設號碼使用。 如果有多個電話號碼，您可以為每位使用者選取預設的電話號碼。 此預設號碼將包含在商務用 Skype 會議邀請中。
  
您可以參閱[設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)，以變更單一使用者的撥入電話號碼。
  
> [!NOTE]
> 國內撥入號碼是專供貴組織使用，而且是唯一可設為預設電話號碼的號碼。 不過，國際撥入號碼可能會跨多個組織共用。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>若要查看您的音訊會議電話號碼

1. 使用您的公司或學校帳戶登入。
    
2. 移至 [系統管理中心] > [**商務用 Skype**]。
    
3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器**]，然後：
    
   - 您可以查看可供音訊會議使用的電話號碼。
    
   - 您也可以查看位置，以及音訊會議自動語音應答將使用的主要和次要語言。
    
> [!NOTE]
> 您可以移至**音訊會議** > **使用者**，然後選取使用者的屬性，以變更預設值，方法是從貴組織中的可用號碼清單中選擇新的號碼。 請參閱[設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將它自動化，您可以使用[CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) Cmdlet。
    
- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
