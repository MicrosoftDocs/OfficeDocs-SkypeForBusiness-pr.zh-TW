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
description: 瞭解如何在團隊中設定 [呼叫我] 功能，讓使用者可以在無法使用電腦音訊的情況下，透過電話加入音訊部分。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cee6937a1bdc2bef6d2184066cb32a4aa94d8e6
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096848"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="6c8cd-103">為您的使用者設定語音來電功能</span><span class="sxs-lookup"><span data-stu-id="6c8cd-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="6c8cd-104">在 Microsoft 團隊中，[**撥號給我**] 功能可讓使用者透過電話加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="6c8cd-105">這在使用音訊電腦的情況下可能很方便。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="6c8cd-106">使用者透過其手機或土地線，以及會議&mdash;的內容部分（例如其他會議參與者共用螢幕或透過電腦播放影片&mdash;），取得會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c8cd-107">在 COVID-19 爆發期間，我們建議使用者按一下 [**加入團隊會議**] 按鈕，而不是使用 PSTN 會議號碼撥入，或使用 [**呼叫我**</strong>] 來加入會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-107">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="6c8cd-108">這主要是因為 COVID-19 所影響之國家/地區的電話架構中的擁塞。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-108">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="6c8cd-109">透過避免 PSTN 通話，您可能會遇到較好的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-109">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="6c8cd-110">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="6c8cd-110">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="6c8cd-111">使用電話進行音訊加入會議</span><span class="sxs-lookup"><span data-stu-id="6c8cd-111">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="6c8cd-112">按一下 [**加入**] 以加入會議，然後按一下 [**選擇您的音訊和影片設定**] 畫面上的 [**電話語音**]。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-112">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="6c8cd-113">使用者可以從這裡進行會議呼叫並加入會議，或將其手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-113">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![[電話語音] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="6c8cd-115">**讓小組會議通話**</span><span class="sxs-lookup"><span data-stu-id="6c8cd-115">**Let the Teams meeting call**</span></span>

<span data-ttu-id="6c8cd-116">在 [**使用電話語音通話**] 畫面上，使用者輸入他們的電話號碼，然後按一下 [**呼叫我**]。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-116">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="6c8cd-117">會議會呼叫使用者並將他們加入會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-117">The meeting calls the user and joins them to the meeting.</span></span>

![[使用電話語音] 畫面上的 [撥號給我] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="6c8cd-119">**手動撥入**</span><span class="sxs-lookup"><span data-stu-id="6c8cd-119">**Dial in manually**</span></span>

<span data-ttu-id="6c8cd-120">加入的另一種方式是直接撥入會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-120">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="6c8cd-121">在 [**使用電話語音通話**] 畫面上，按一下 [**手動撥**入]，取得電話號碼的清單，以供撥入會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-121">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動撥號] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="6c8cd-123">在會議期間音訊出現問題時，進行回撥</span><span class="sxs-lookup"><span data-stu-id="6c8cd-123">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="6c8cd-124">如果使用者在會議期間使用電腦時遇到音訊問題，使用者可以輕鬆地切換到使用電話進行音訊。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-124">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="6c8cd-125">團隊會偵測到發生音訊或設備問題的時間，並將使用者重新導向以使用其手機，只要顯示 [**呼叫給我**] 選項即可。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-125">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="6c8cd-126">以下是當小組無法偵測到麥克風時，顯示的訊息和 [**撥號給我**] 選項的範例。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-126">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![[向我回電] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="6c8cd-128">使用者按一下 [**回電給我**]，這會顯示 [**使用電話語音**播放] 畫面。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-128">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="6c8cd-129">您可以從這裡輸入他們的電話號碼，並讓團隊會議通話，然後將他們加入會議或手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-129">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="6c8cd-130">設定 [撥號給我] 功能</span><span class="sxs-lookup"><span data-stu-id="6c8cd-130">Set up the Call me feature</span></span>

<span data-ttu-id="6c8cd-131">若要為貴組織中的使用者啟用 [撥號給我] 功能，必須進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="6c8cd-131">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="6c8cd-132">針對組織中排程會議的使用者（會議召集人）啟用音訊會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-132">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="6c8cd-133">若要深入瞭解，請參閱在小組中[設定音訊會議](set-up-audio-conferencing-in-teams.md)，以及[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-133">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="6c8cd-134">使用者可以從會議撥出。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-134">Users can dial out from meetings.</span></span> <span data-ttu-id="6c8cd-135">若要深入瞭解，請參閱[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-135">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="6c8cd-136">如果使用者沒有啟用 [從會議撥出]，則無法使用 [撥號**給我**] 選項，而且使用者將不會收到邀請加入會議的電話。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-136">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="6c8cd-137">相反地，使用者會在 [**使用電話語音**] 畫面上看到電話號碼清單，讓他們可以用來在手機上手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="6c8cd-137">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
