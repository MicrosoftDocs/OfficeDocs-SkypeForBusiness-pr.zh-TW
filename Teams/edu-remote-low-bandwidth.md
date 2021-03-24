---
title: Microsoft Teams 教育版的低頻寬指導方針
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Microsoft Teams 教育版文章，有助於解決與低頻寬有關的會議和影片問題。 無論您身為家長、老師還是 IT 系統管理員，都有選項可改善 Teams 的使用體驗。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: b254bfb89a96efed65e2c1fdba1c345825d81dc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111079"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="f6155-104">協助 Teams 教育版的低頻寬情況</span><span class="sxs-lookup"><span data-stu-id="f6155-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="f6155-105">在使用 Microsoft Teams 時，有許多可能會影響效能的網路元素，而低頻寬正是可能會讓您覺得完全失控的其中一種情況。</span><span class="sxs-lookup"><span data-stu-id="f6155-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="f6155-106">請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="f6155-106">Consider the following:</span></span>

- <span data-ttu-id="f6155-107">學校的低速網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="f6155-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="f6155-108">一或多個學生的低速網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="f6155-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="f6155-109">一天當中不時會因為某個區域的網路使用量而導致低頻寬的情形。</span><span class="sxs-lookup"><span data-stu-id="f6155-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="f6155-110">不是學校和學生所引起的服務中斷而導致低頻寬期間，雖然如此，但仍影響到效能。</span><span class="sxs-lookup"><span data-stu-id="f6155-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="f6155-111">偽裝成低頻寬問題的非頻寬問題 (例如硬體問題)。</span><span class="sxs-lookup"><span data-stu-id="f6155-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="f6155-112">本文會針對各種 Teams 活動，提供當您遇到低頻寬問題時可以遵循的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="f6155-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6155-113">這裡有 [Microsoft Teams 如何使用記憶體](teams-memory-usage-perf.md)的相關資訊，因為除了低頻寬問題外，您的裝置也可能遇到資源問題。</span><span class="sxs-lookup"><span data-stu-id="f6155-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="f6155-114">如果您要尋找 Microsoft Teams 的網路指導方針，請檢閱[針對 Microsoft Teams 準備組織的網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="f6155-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="f6155-115">解決 IT 系統管理員的低頻寬問題</span><span class="sxs-lookup"><span data-stu-id="f6155-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="f6155-116">請務必牢記，身為 IT 系統管理員，雖然您有各式各樣能迅速解決問題的低頻寬問題解決方案，但使用前請先仔細思考，因為有些問題或許在更為限縮的老師或甚至是學生/家長層級就能夠解決。</span><span class="sxs-lookup"><span data-stu-id="f6155-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="f6155-117">簡言之，如果是眾多學生遇到低頻寬問題，那麼以 IT 系統管理員的角色來採取行動便很合理，同樣地，如果在學生/老師層級採取行動沒有用，則以 IT 系統管理員的角色來採取行動也很合理。</span><span class="sxs-lookup"><span data-stu-id="f6155-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="f6155-118">如果您有空，[體驗品質的審查指南](quality-of-experience-review-guide.md)值得一讀 (這雖非教育版專用指南，但仍有寶貴資訊)。</span><span class="sxs-lookup"><span data-stu-id="f6155-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="f6155-119">這可讓有經驗的 IT 系統管理員深入了解其老師和學生所獲得的體驗。</span><span class="sxs-lookup"><span data-stu-id="f6155-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="f6155-120">會議與影片</span><span class="sxs-lookup"><span data-stu-id="f6155-120">Meetings and video</span></span>

<span data-ttu-id="f6155-121">低頻寬問題的主要焦點在會議，尤其是會議中播放的影片。</span><span class="sxs-lookup"><span data-stu-id="f6155-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="f6155-122">當 IT 系統管理員在處理學生或老師所報告，有關要在教育設定下獲得最佳會議體驗的問題時，應考慮以下某些動作。</span><span class="sxs-lookup"><span data-stu-id="f6155-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="f6155-123">會議原則</span><span class="sxs-lookup"><span data-stu-id="f6155-123">Meeting policies</span></span>

<span data-ttu-id="f6155-124">就會議而言，低頻寬情況最令人擔憂的其中一點是播放影片。</span><span class="sxs-lookup"><span data-stu-id="f6155-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="f6155-125">幸運的是，Teams 可自動針對所偵測到的頻寬來擴縮，不僅如此，身為 IT 系統管理員，您也可以在每一召集人和/或每一使用者層級設定原則選項，讓每個人都能根據其在給定時間所使用的頻寬，而獲得最佳使用體驗。</span><span class="sxs-lookup"><span data-stu-id="f6155-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="f6155-126">可透過原則來設定的部分內容包括：</span><span class="sxs-lookup"><span data-stu-id="f6155-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="f6155-127">完全停用影片，讓所有人都無法啟用影片。</span><span class="sxs-lookup"><span data-stu-id="f6155-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="f6155-128">媒體位元速率 (根據每位使用者來加以設定)。</span><span class="sxs-lookup"><span data-stu-id="f6155-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="f6155-129">若要深入了解您的選項，並逐步查看必須為會議和影片設定的具體原則，請參閱 [Teams 中的會議原則設定：音訊和影片](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video)，以取得詳細的逐步說明資訊。</span><span class="sxs-lookup"><span data-stu-id="f6155-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="f6155-130">螢幕共用原則</span><span class="sxs-lookup"><span data-stu-id="f6155-130">Screen sharing policies</span></span>

<span data-ttu-id="f6155-131">在其他情況下，老師可能會與學生共用其整個螢幕，這個時候，共用範圍應限制在與所授課程有關的應用程式上。</span><span class="sxs-lookup"><span data-stu-id="f6155-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="f6155-132">如果不想讓老師個別做選擇，而是有其他更想要的方式，那麼您也可以透過原則來設定此限制。</span><span class="sxs-lookup"><span data-stu-id="f6155-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="f6155-133">若要了解有什麼好方法可以讓您透過原則設定來限制螢幕共用，請參閱 [Teams 中的會議原則設定：螢幕共用](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video)。</span><span class="sxs-lookup"><span data-stu-id="f6155-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="f6155-134">會議的撥入號碼</span><span class="sxs-lookup"><span data-stu-id="f6155-134">Dial-in number for meetings</span></span>

<span data-ttu-id="f6155-135">讓某些學生嘗試撥入某些教室工作階段可能會更方便。</span><span class="sxs-lookup"><span data-stu-id="f6155-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="f6155-136">您可以為 Teams 會議提供撥入號碼，讓想要發問的學生可以打電話進來而非參加視訊會議。</span><span class="sxs-lookup"><span data-stu-id="f6155-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="f6155-137">如需這方面的詳細資訊，請參閱[將電話號碼設定為包含在 Microsoft Teams 的邀請中](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="f6155-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="f6155-138">身為老師的低頻寬案例</span><span class="sxs-lookup"><span data-stu-id="f6155-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="f6155-139">老師應該會覺得他們有能力採取某些步驟來解決低頻寬問題，而且在下列情況時，可能是比由 IT 系統管理員採取行動還要好的選擇：</span><span class="sxs-lookup"><span data-stu-id="f6155-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="f6155-140">如果問題間歇發生，或持續時間相對短暫。</span><span class="sxs-lookup"><span data-stu-id="f6155-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="f6155-141">如果您預料當天的特定時間會發生問題，或可以一定程度地預測到低頻寬期間。</span><span class="sxs-lookup"><span data-stu-id="f6155-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="f6155-142">如果有這些情況，您就可以採取某些動作。</span><span class="sxs-lookup"><span data-stu-id="f6155-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="f6155-143">如需詳細資訊，請參閱[在低頻寬時使用 Teams 來完成學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。</span><span class="sxs-lookup"><span data-stu-id="f6155-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="f6155-144">身為家長或學生的低頻寬案例</span><span class="sxs-lookup"><span data-stu-id="f6155-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="f6155-145">也有一些情況是您應該主動與老師討論的，因為頻寬問題可能是出在學生這邊 (例如，大量學生能夠正常觀看影片課程，但少數學生卻會發生問題)。</span><span class="sxs-lookup"><span data-stu-id="f6155-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="f6155-146">希望許多家長有能力排解這些問題並不合理，而且低頻寬問題可能不是學生或家長能夠控制的 (其住家可能無法存取高頻寬、其附近可能有很多人使用頻寬而影響其可以採取的行動、網際網路可能不穩定等等)。</span><span class="sxs-lookup"><span data-stu-id="f6155-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="f6155-147">我們也將家長和學生的指導方針一起放在[在低頻寬時使用 Teams 來完成學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)一文內供您檢閱，如果遇到任何問題，則可以嘗試這些建議。</span><span class="sxs-lookup"><span data-stu-id="f6155-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>