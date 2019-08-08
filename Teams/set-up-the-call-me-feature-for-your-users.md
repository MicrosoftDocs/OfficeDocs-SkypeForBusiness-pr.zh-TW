---
title: 為您的使用者設定 [撥號給我] 功能
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在團隊中設定 [呼叫我] 功能, 讓使用者可以在無法使用電腦音訊的情況下, 透過電話加入音訊部分。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54e9d90a3380358abd0c1e984b90834455eb44e2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243170"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="d6848-103">為您的使用者設定 [撥號給我] 功能</span><span class="sxs-lookup"><span data-stu-id="d6848-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="d6848-104">在 Microsoft 團隊中, [**撥號給我**] 功能可讓使用者透過電話加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="d6848-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="d6848-105">這在使用音訊電腦的情況下可能很方便。</span><span class="sxs-lookup"><span data-stu-id="d6848-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="d6848-106">使用者透過其手機或土地線, 以及會議&mdash;的內容部分 (例如其他會議參與者共用螢幕或透過電腦播放影片&mdash;), 取得會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="d6848-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="d6848-107">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="d6848-107">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="d6848-108">使用電話進行音訊加入會議</span><span class="sxs-lookup"><span data-stu-id="d6848-108">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="d6848-109">按一下 [**加入**] 以加入會議, 然後按一下 [**選擇您的音訊和影片設定**] 畫面上的 [**電話語音**]。</span><span class="sxs-lookup"><span data-stu-id="d6848-109">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="d6848-110">使用者可以從這裡進行會議呼叫並加入會議, 或將其手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d6848-110">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![[電話語音] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="d6848-112">**讓小組會議通話**</span><span class="sxs-lookup"><span data-stu-id="d6848-112">**Let the Teams meeting call**</span></span>

<span data-ttu-id="d6848-113">在 [**使用電話語音通話**] 畫面上, 使用者輸入他們的電話號碼, 然後按一下 [**呼叫我**]。</span><span class="sxs-lookup"><span data-stu-id="d6848-113">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="d6848-114">會議會呼叫使用者並將他們加入會議。</span><span class="sxs-lookup"><span data-stu-id="d6848-114">The meeting calls the user and joins them to the meeting.</span></span>

![[使用電話語音] 畫面上的 [撥號給我] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="d6848-116">**手動撥入**</span><span class="sxs-lookup"><span data-stu-id="d6848-116">**Dial in manually**</span></span>

<span data-ttu-id="d6848-117">加入的另一種方式是直接撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d6848-117">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="d6848-118">在 [**使用電話語音通話**] 畫面上, 按一下 [**手動撥**入], 取得電話號碼的清單, 以供撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d6848-118">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動撥號] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="d6848-120">在會議期間音訊出現問題時, 進行回撥</span><span class="sxs-lookup"><span data-stu-id="d6848-120">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="d6848-121">如果使用者在會議期間使用電腦時遇到音訊問題, 使用者可以輕鬆地切換到使用電話進行音訊。</span><span class="sxs-lookup"><span data-stu-id="d6848-121">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="d6848-122">團隊會偵測到發生音訊或設備問題的時間, 並將使用者重新導向以使用其手機, 只要顯示 [**呼叫給我**] 選項即可。</span><span class="sxs-lookup"><span data-stu-id="d6848-122">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="d6848-123">以下是當小組無法偵測到麥克風時, 顯示的訊息和 [**撥號給我**] 選項的範例。</span><span class="sxs-lookup"><span data-stu-id="d6848-123">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![[向我回電] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="d6848-125">使用者按一下 [**回電給我**], 這會顯示 [**使用電話語音**播放] 畫面。</span><span class="sxs-lookup"><span data-stu-id="d6848-125">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="d6848-126">您可以從這裡輸入他們的電話號碼, 並讓團隊會議通話, 然後將他們加入會議或手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d6848-126">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="d6848-127">設定 [撥號給我] 功能</span><span class="sxs-lookup"><span data-stu-id="d6848-127">Set up the Call me feature</span></span>

<span data-ttu-id="d6848-128">若要為貴組織中的使用者啟用 [撥號給我] 功能, 必須進行下列設定:</span><span class="sxs-lookup"><span data-stu-id="d6848-128">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="d6848-129">針對組織中排程會議的使用者 (會議召集人) 啟用音訊會議。</span><span class="sxs-lookup"><span data-stu-id="d6848-129">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="d6848-130">若要深入瞭解, 請參閱在小組中[設定音訊會議](set-up-audio-conferencing-in-teams.md), 以及[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d6848-130">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="d6848-131">使用者可以從會議撥出。</span><span class="sxs-lookup"><span data-stu-id="d6848-131">Users can dial out from meetings.</span></span> <span data-ttu-id="d6848-132">若要深入瞭解, 請參閱[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d6848-132">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="d6848-133">如果使用者沒有啟用 [從會議撥出], 則無法使用 [撥號**給我**] 選項, 而且使用者將不會收到邀請加入會議的電話。</span><span class="sxs-lookup"><span data-stu-id="d6848-133">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="d6848-134">相反地, 使用者會在 [**使用電話語音**] 畫面上看到電話號碼清單, 讓他們可以用來在手機上手動撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d6848-134">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
