---
title: 在商務用 Skype Online 中設定音訊會議自動語音服務語言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
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
description: 瞭解如何在商務用 Skype Online 中為音訊會議號碼選取音訊會議自動語音服務語言。
ms.openlocfilehash: d2b4c0d9be666a6ee7de9c2bd36b8dd06cccdf32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109995"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="e4845-103">在商務用 Skype Online 中設定音訊會議自動語音服務語言</span><span class="sxs-lookup"><span data-stu-id="e4845-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e4845-104">有關在 Microsoft Teams 中設定自動語音翻譯語言的資訊，請參閱在 Microsoft Teams 中設定音訊會議 [自動語音語音處理語言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="e4845-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="e4845-105">商務用 Skype 的音訊會議自動語音機可在語音來電者加入會議時，以多種語言向來電者致意。</span><span class="sxs-lookup"><span data-stu-id="e4845-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="e4845-106">選擇一種主要語言，最多四種次要語言。</span><span class="sxs-lookup"><span data-stu-id="e4845-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="e4845-107">您設定的主要語言會先使用，而次要語言會由自動翻譯使用，以便您選取。</span><span class="sxs-lookup"><span data-stu-id="e4845-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="e4845-108">您只可以變更專屬類別之音訊會議號碼的語言。</span><span class="sxs-lookup"><span data-stu-id="e4845-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="e4845-109">無法變更共用音訊會議號碼的語言。</span><span class="sxs-lookup"><span data-stu-id="e4845-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="e4845-110">設定會議自動語音服務語言</span><span class="sxs-lookup"><span data-stu-id="e4845-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="e4845-111">您必須是全域[系統管理員或](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)[商務用 Skype 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="e4845-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="e4845-112">在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="e4845-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="e4845-113">進入舊版入口網站後，選取 **[音訊會議**，然後按一下 **Microsoft 橋接器**。</span><span class="sxs-lookup"><span data-stu-id="e4845-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="e4845-114">從清單中選取音訊會議電話號碼，然後按一下 [動作窗格設定 **語言**> 。</span><span class="sxs-lookup"><span data-stu-id="e4845-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="e4845-115">只能變更專用音訊會議號碼的語言。</span><span class="sxs-lookup"><span data-stu-id="e4845-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="e4845-116">在 [ **設定語言>** 頁面上，按一下 **[主要** 語言清單> 以查看可用語言的完整清單。</span><span class="sxs-lookup"><span data-stu-id="e4845-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="e4845-117">如果需要，請按一下每個次要 **語言清單以** 選取次要語言。</span><span class="sxs-lookup"><span data-stu-id="e4845-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4845-118">系統列出支援的主要和次要語言。</span><span class="sxs-lookup"><span data-stu-id="e4845-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="e4845-119">在清單中選取它們的順序，就是呈現給來電者的語言順序。</span><span class="sxs-lookup"><span data-stu-id="e4845-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="e4845-120">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="e4845-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="e4845-121">想要我應該知道嗎？</span><span class="sxs-lookup"><span data-stu-id="e4845-121">Want else should I know?</span></span>

- <span data-ttu-id="e4845-122">若要查看音訊會議支援的語言清單，請參閱 [音訊會議支援的語言](/MicrosoftTeams/audio-conferencing-supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="e4845-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="e4845-123">語言可以設定為專用，但不能設定為共用電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e4845-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="e4845-124">若要查看在 Microsoft 365 或 Office 365 中提供使用 Microsoft 作為提供者的音訊會議可用的國家/地區清單，請參閱音訊會議 [的電話號碼](phone-numbers-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="e4845-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="e4845-125">想要使用 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="e4845-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="e4845-126">若要自動化此步驟，您可以使用 [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) 和 [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) Cmdlets。</span><span class="sxs-lookup"><span data-stu-id="e4845-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) and [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlets.</span></span>
  
<span data-ttu-id="e4845-127">若要深入瞭解，請參閱 [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e4845-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e4845-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="e4845-128">Related topics</span></span>

[<span data-ttu-id="e4845-129">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="e4845-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)