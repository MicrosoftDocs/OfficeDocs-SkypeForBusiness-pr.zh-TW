---
title: 在商務用 Skype Online 中設定音訊會議的自動助理語言
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
description: 瞭解如何在商務用 Skype Online 中為音訊會議編號選取音訊會議自動語音應答語言。
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163898"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="d50e4-103">在商務用 Skype Online 中設定音訊會議的自動助理語言</span><span class="sxs-lookup"><span data-stu-id="d50e4-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="d50e4-104">如需在 Microsoft 團隊中設定自動助理語言的相關資訊，請參閱[在 Microsoft 團隊中設定音訊會議的自動助理語言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="d50e4-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="d50e4-105">商務用 Skype 的音訊會議自動語音應答，在加入會議時，可以向音訊撥號者使用多種不同的語言。</span><span class="sxs-lookup"><span data-stu-id="d50e4-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="d50e4-106">選擇一種主要語言，以及最多四個次要語言。</span><span class="sxs-lookup"><span data-stu-id="d50e4-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="d50e4-107">您首先會使用您所設定的主要語言，並依您選取的順序，自動助理會使用次要語言。</span><span class="sxs-lookup"><span data-stu-id="d50e4-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="d50e4-108">您只能變更專用類別之音訊會議號碼的語言。</span><span class="sxs-lookup"><span data-stu-id="d50e4-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="d50e4-109">無法變更共用音訊會議號碼的語言。</span><span class="sxs-lookup"><span data-stu-id="d50e4-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="d50e4-110">設定會議自動語音應答語言</span><span class="sxs-lookup"><span data-stu-id="d50e4-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="d50e4-111">您必須是[全域系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或[商務用 Skype 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能執行這個步驟。</span><span class="sxs-lookup"><span data-stu-id="d50e4-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="d50e4-112">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**舊版入口網站**]。</span><span class="sxs-lookup"><span data-stu-id="d50e4-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="d50e4-113">在舊版入口網站中，選取 [**音訊會議**]，然後按一下 [ **Microsoft 橋接器**]。</span><span class="sxs-lookup"><span data-stu-id="d50e4-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="d50e4-114">從清單中選取音訊會議電話號碼，然後在 [動作] 窗格中，按一下 [**設定語言**]。</span><span class="sxs-lookup"><span data-stu-id="d50e4-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="d50e4-115">只可以變更專用音訊會議號碼的語言。</span><span class="sxs-lookup"><span data-stu-id="d50e4-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="d50e4-116">在 [**設定語言**] 頁面上，按一下 [**主要語言**] 清單，以查看可用語言的完整清單。</span><span class="sxs-lookup"><span data-stu-id="d50e4-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="d50e4-117">如有需要，請按一下每個**次要語言**清單，選取 [次要語言]。</span><span class="sxs-lookup"><span data-stu-id="d50e4-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d50e4-118">列出支援的主要和次要語言。</span><span class="sxs-lookup"><span data-stu-id="d50e4-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="d50e4-119">您在清單中選取它們的順序就會是提供給呼叫者的語言順序。</span><span class="sxs-lookup"><span data-stu-id="d50e4-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="d50e4-120">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d50e4-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="d50e4-121">還需要知道嗎？</span><span class="sxs-lookup"><span data-stu-id="d50e4-121">Want else should I know?</span></span>

- <span data-ttu-id="d50e4-122">若要查看音訊會議支援的語言清單，請參閱[音訊會議支援的語言](/MicrosoftTeams/audio-conferencing-supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="d50e4-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="d50e4-123">您可以將 [語言] 設定為 [專用]，而不是用於共用的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d50e4-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="d50e4-124">若要查看在 Microsoft 365 或 Office 365 中使用 Microsoft 作為提供者的音訊會議的國家/地區清單，請參閱[音訊會議的電話號碼](phone-numbers-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="d50e4-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="d50e4-125">想要使用 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="d50e4-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="d50e4-126">若要自動化此步驟，您可以使用[CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[get-csonlinedialinconferencinglanguagessupported](https://go.microsoft.com/fwlink/?LinkId=617684) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d50e4-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) and [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="d50e4-127">若要深入瞭解，請參閱[使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="d50e4-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d50e4-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="d50e4-128">Related topics</span></span>

[<span data-ttu-id="d50e4-129">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="d50e4-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
