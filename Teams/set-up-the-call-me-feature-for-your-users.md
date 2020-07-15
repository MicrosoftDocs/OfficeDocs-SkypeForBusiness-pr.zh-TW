---
title: 為您的使用者設定語音來電功能
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在團隊中設定 [呼叫我] 功能，讓使用者可以透過電話在使用電腦音訊時加入音訊部分。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138013"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="9ea9c-103">為您的使用者設定語音來電功能</span><span class="sxs-lookup"><span data-stu-id="9ea9c-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="9ea9c-104">在 Microsoft 團隊中，[**撥號給我**] 功能可讓使用者透過電話加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="9ea9c-105">這在使用音訊電腦的情況下可能很方便。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="9ea9c-106">使用者透過其手機或土地線，以及會議的內容部分 &mdash; （例如當其他會議參與者分享其螢幕或透過其電腦播放影片），來取得會議的音訊部分 &mdash; 。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="9ea9c-107">在大量會議（我們已與 COVID-19 的病毒發作）期間，我們建議使用者按一下 [<strong>加入團隊會議</strong>] 按鈕，而不是使用 PSTN 會議號碼撥入，或使用 [<strong>呼叫我</strong>] 來加入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="9ea9c-108">這有助於在大量會議造成 PSTN 網路擁塞時確保音訊品質。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9ea9c-109">在 COVID-19 疫情爆發期間，我們建議使用者按一下 [加入 Teams 會議]\*\*\*\* 按鈕，而不要使用 PSTN 會議號碼或使用 [撥號給我]\*\*\*\*</strong> 來加入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="9ea9c-110">這主要是因為受到 COVID-19 影響的國家/地區電話語音架構擁塞。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="9ea9c-111">藉由避免 PSTN 通話，您可能會體驗到更好的音質。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="9ea9c-112">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="9ea9c-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="9ea9c-113">使用電話進行音訊加入會議</span><span class="sxs-lookup"><span data-stu-id="9ea9c-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="9ea9c-114">按一下 [**加入**] 以加入會議，然後按一下 [**選擇您的音訊和影片設定**] 畫面上的 [**電話語音**]。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="9ea9c-115">使用者可以從這裡進行會議呼叫並加入會議，或將其手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![[電話語音] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="9ea9c-117">**讓小組會議通話**</span><span class="sxs-lookup"><span data-stu-id="9ea9c-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="9ea9c-118">在 [**使用電話語音通話**] 畫面上，使用者輸入他們的電話號碼，然後按一下 [**呼叫我**]。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="9ea9c-119">會議會呼叫使用者並將他們加入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-119">The meeting calls the user and joins them to the meeting.</span></span>

![[使用電話語音] 畫面上的 [撥號給我] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="9ea9c-121">**手動撥入**</span><span class="sxs-lookup"><span data-stu-id="9ea9c-121">**Dial in manually**</span></span>

<span data-ttu-id="9ea9c-122">加入的另一種方式是直接撥入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="9ea9c-123">在 [**使用電話語音通話**] 畫面上，按一下 [**手動撥**入]，取得電話號碼的清單，以供撥入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動撥號] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="9ea9c-125">在會議期間音訊出現問題時，進行回撥</span><span class="sxs-lookup"><span data-stu-id="9ea9c-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="9ea9c-126">如果使用者在會議期間使用電腦時遇到音訊問題，使用者可以輕鬆地切換到使用電話進行音訊。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="9ea9c-127">團隊會偵測到發生音訊或設備問題的時間，並將使用者重新導向以使用其手機，只要顯示 [**呼叫給我**] 選項即可。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="9ea9c-128">以下是當小組無法偵測到麥克風時，顯示的訊息和 [**撥號給我**] 選項的範例。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![[向我回電] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="9ea9c-130">使用者按一下 [**回電給我**]，這會顯示 [**使用電話語音**播放] 畫面。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="9ea9c-131">您可以從這裡輸入他們的電話號碼，並讓團隊會議通話，然後將他們加入會議或手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="9ea9c-132">設定 [撥號給我] 功能</span><span class="sxs-lookup"><span data-stu-id="9ea9c-132">Set up the Call me feature</span></span>

<span data-ttu-id="9ea9c-133">若要為貴組織中的使用者啟用 [撥號給我] 功能，必須進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="9ea9c-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="9ea9c-134">針對組織中排程會議的使用者（會議召集人）啟用音訊會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="9ea9c-135">若要深入瞭解，請參閱在小組中[設定音訊會議](set-up-audio-conferencing-in-teams.md)，以及[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="9ea9c-136">使用者可以從會議撥出。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-136">Users can dial out from meetings.</span></span> <span data-ttu-id="9ea9c-137">若要深入瞭解，請參閱[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="9ea9c-138">如果使用者沒有啟用 [從會議撥出]，則無法使用 [撥號**給我**] 選項，而且使用者將不會收到邀請加入會議的電話。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="9ea9c-139">相反地，使用者會在 [**使用電話語音**] 畫面上看到電話號碼清單，讓他們可以用來在手機上手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="9ea9c-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
