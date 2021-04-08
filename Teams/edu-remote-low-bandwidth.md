---
title: Microsoft Teams 教育版的低頻寬指導方針
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Microsoft Teams 教育版文章，有助於解決與低頻寬有關的會議和視訊問題。 無論您身為家長、老師還是 IT 系統管理員，都可有改善 Teams 使用體驗的選項。
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
ms.openlocfilehash: 17520645f23500550c6bc991c9d25ad2f72b2b6e
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598422"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="9ec44-104">協助解決 Teams 教育版的低頻寬情況。</span><span class="sxs-lookup"><span data-stu-id="9ec44-104">Help for low-bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="9ec44-105">在使用 Microsoft Teams 時，有許多可能會影響效能的網路元素。</span><span class="sxs-lookup"><span data-stu-id="9ec44-105">There are numerous network elements when it comes to working with Microsoft Teams that can affect performance.</span></span> <span data-ttu-id="9ec44-106">而低頻寬正是可能會讓您覺得完全失控的其中一種情況。</span><span class="sxs-lookup"><span data-stu-id="9ec44-106">Low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="9ec44-107">請考慮下列狀況：</span><span class="sxs-lookup"><span data-stu-id="9ec44-107">Consider the following situations:</span></span>

- <span data-ttu-id="9ec44-108">學校的低速網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="9ec44-108">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="9ec44-109">一或多個學生的低速網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="9ec44-109">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="9ec44-110">一天當中不時會因為某個區域的網路使用量而導致低頻寬的情形。</span><span class="sxs-lookup"><span data-stu-id="9ec44-110">Times of the day when there's low bandwidth because of network usage in an area.</span></span>
- <span data-ttu-id="9ec44-111">不是學校和學生所引起的服務中斷而導致低頻寬期間，雖然如此，但仍影響到效能。</span><span class="sxs-lookup"><span data-stu-id="9ec44-111">Low-bandwidth periods because of outages local to neither the school nor to students, but, which affect performance nonetheless.</span></span>
- <span data-ttu-id="9ec44-112">偽裝成低頻寬問題的非頻寬問題 (例如硬體問題)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-112">Non-bandwidth issues (for example, issues with hardware) that masquerade as low-bandwidth issues.</span></span>

<span data-ttu-id="9ec44-113">本文會針對各種 Teams 活動，提供當您遇到低頻寬問題時可以遵循的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="9ec44-113">This article will give you best practices to follow for various Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ec44-114">這裡有 [Microsoft Teams 如何使用記憶體](teams-memory-usage-perf.md)的相關資訊，因為除了低頻寬問題外，您的裝置也可能遇到資源問題。</span><span class="sxs-lookup"><span data-stu-id="9ec44-114">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="9ec44-115">如果您要尋找 Microsoft Teams 的網路指導方針，請檢閱[針對 Microsoft Teams 準備組織的網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-115">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-admins"></a><span data-ttu-id="9ec44-116">為 IT 系統管理員解決低頻寬問題</span><span class="sxs-lookup"><span data-stu-id="9ec44-116">Resolving low-bandwidth issues for Admins</span></span>

<span data-ttu-id="9ec44-117">身為 IT 系統管理員，請務必記得，儘管您擁有廣泛解決的低頻寬問題的解決方案，可以迅速解決問題，但應仔細考慮解決方案。</span><span class="sxs-lookup"><span data-stu-id="9ec44-117">The important thing to remember, as an IT Admin, is that while you have solutions for low-bandwidth issues that are wide-spread that will resolve problems quickly, solutions should be considered carefully.</span></span> <span data-ttu-id="9ec44-118">在老師甚至學生/家長層面上，可能可以更集中地解決某些問題。</span><span class="sxs-lookup"><span data-stu-id="9ec44-118">Some issues may be able to resolve with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="9ec44-119">簡言之，如果是眾多學生遇到低頻寬問題，那麼以 IT 系統管理員的角色來採取行動便很合理，同樣地，如果在學生/老師層級採取行動沒有用，則以 IT 系統管理員的角色來採取行動也很合理。</span><span class="sxs-lookup"><span data-stu-id="9ec44-119">In short, if the low-bandwidth issue occurs for a wide group of students, taking action as an IT Admin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="9ec44-120">如果您有空，[體驗品質的審查指南](quality-of-experience-review-guide.md)值得一讀 (這雖非教育版專用指南，但仍有寶貴資訊)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-120">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="9ec44-121">本指南可讓有經驗的 IT 系統管理員深入了解老師和學生所獲得的體驗。</span><span class="sxs-lookup"><span data-stu-id="9ec44-121">This guide will allow experienced IT Admins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="9ec44-122">會議與視訊</span><span class="sxs-lookup"><span data-stu-id="9ec44-122">Meetings and video</span></span>

<span data-ttu-id="9ec44-123">低頻寬問題的主要焦點在會議，尤其是會議中進行的視訊。</span><span class="sxs-lookup"><span data-stu-id="9ec44-123">A primary focus for low-bandwidth issues is meetings; specifically, video in meetings.</span></span> <span data-ttu-id="9ec44-124">在處理學生或老師報告的，有關在教育環境中獲得最佳會議體驗的問題時，IT 系統管理員應考慮以下動作。</span><span class="sxs-lookup"><span data-stu-id="9ec44-124">An IT Admin should consider the actions below when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="9ec44-125">會議原則</span><span class="sxs-lookup"><span data-stu-id="9ec44-125">Meeting policies</span></span>

<span data-ttu-id="9ec44-126">就會議而言，低頻寬情況最令人擔憂的其中一點就是進行視訊。</span><span class="sxs-lookup"><span data-stu-id="9ec44-126">Regarding meetings, one of the most concerning areas for low-bandwidth situations has to do with videos.</span></span> <span data-ttu-id="9ec44-127">除了 Teams 能夠自動調整為偵測到的頻寬之外，您作為 IT 系統管理員，還有可在每個召集人和/或每位使用者層級設定的原則選項。</span><span class="sxs-lookup"><span data-stu-id="9ec44-127">In addition to Teams being able to scale to detected bandwidth automatically, you as an IT Admin have policy options you can set at the per-organizer and/or per-user level.</span></span> <span data-ttu-id="9ec44-128">這些選項使您可以根據每個人在給定時間必須使用的頻寬，為他們提供最佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="9ec44-128">These options allow you to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="9ec44-129">可透過原則來設定的部分內容包括：</span><span class="sxs-lookup"><span data-stu-id="9ec44-129">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="9ec44-130">完全停用影片，讓所有人都無法啟用影片。</span><span class="sxs-lookup"><span data-stu-id="9ec44-130">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="9ec44-131">媒體位元速率 (根據每位使用者設定)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-131">Media bit rate (this setting is set per-user).</span></span>

<span data-ttu-id="9ec44-132">若要深入了解您的選項，並逐步查看必須為會議和視訊設定的具體原則，請參閱 [Teams 中的會議原則設定：音訊和視訊](meeting-policies-audio-and-video.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-132">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="9ec44-133">螢幕共用原則</span><span class="sxs-lookup"><span data-stu-id="9ec44-133">Screen sharing policies</span></span>

<span data-ttu-id="9ec44-134">在其他情況下，老師可能會與學生共用其整個螢幕，這個時候，共用範圍應限制在與所授課程有關的應用程式上。</span><span class="sxs-lookup"><span data-stu-id="9ec44-134">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="9ec44-135">也可以透過原則來設定此設定，如果這樣做是比讓老師單獨進行選擇更可取的方法。</span><span class="sxs-lookup"><span data-stu-id="9ec44-135">This setting can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="9ec44-136">有關您可以透過原則設定限制螢幕畫面分享的方法的好主意，請查看 [Teams 中的會議原則設定：音訊與視訊](meeting-policies-audio-and-video.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-136">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="9ec44-137">會議的撥入號碼</span><span class="sxs-lookup"><span data-stu-id="9ec44-137">Dial-in number for meetings</span></span>

<span data-ttu-id="9ec44-138">讓某些學生嘗試撥入某些教室工作階段可能會更方便。</span><span class="sxs-lookup"><span data-stu-id="9ec44-138">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="9ec44-139">您可以為 Teams 會議提供撥入號碼，讓想要發問的學生可以打電話進來而非參加視訊會議。</span><span class="sxs-lookup"><span data-stu-id="9ec44-139">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="9ec44-140">如需這方面的詳細資訊，請參閱[將電話號碼設定為包含在 Microsoft Teams 的邀請中](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-140">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="9ec44-141">身為老師的低頻寬案例</span><span class="sxs-lookup"><span data-stu-id="9ec44-141">Low-bandwidth scenarios as an educator</span></span>

<span data-ttu-id="9ec44-142">老師應該會覺得他們有能力採取某些步驟來解決低頻寬問題，而且在下列情況時，可能是比由 IT 系統管理員採取行動還要好的選擇：</span><span class="sxs-lookup"><span data-stu-id="9ec44-142">Educators should feel empowered to take steps to resolve low-bandwidth issues, and may be a superior choice to IT Admin action in the following situations:</span></span>

- <span data-ttu-id="9ec44-143">如果問題間歇發生，或持續時間相對短暫。</span><span class="sxs-lookup"><span data-stu-id="9ec44-143">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="9ec44-144">如果您預料當天的特定時間會發生問題，或可以一定程度地預測到低頻寬期間。</span><span class="sxs-lookup"><span data-stu-id="9ec44-144">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="9ec44-145">如果有這些情況，您就可以採取某些動作。</span><span class="sxs-lookup"><span data-stu-id="9ec44-145">In these situations, you can take some actions.</span></span>

<span data-ttu-id="9ec44-146">如需詳細資訊，請參閱[在低頻寬時使用 Teams 來完成學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-146">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="9ec44-147">身為家長或學生的低頻寬案例</span><span class="sxs-lookup"><span data-stu-id="9ec44-147">Low-bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="9ec44-148">也有一些情況是您應該主動與老師討論的，因為頻寬問題可能是出在學生這邊 (例如，大量學生能夠正常觀看影片課程，但少數學生卻會發生問題)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-148">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="9ec44-149">預期許多家長能夠疑難排解這些問題並不合理。</span><span class="sxs-lookup"><span data-stu-id="9ec44-149">It's not reasonable to expect many parents to be able to troubleshoot these issues.</span></span> <span data-ttu-id="9ec44-150">低頻寬問題可能不是學生或家長能夠控制的 (其住家可能無法存取高頻寬、其附近可能有很多人使用頻寬而影響其可以採取的行動、網際網路可能不穩定等等)。</span><span class="sxs-lookup"><span data-stu-id="9ec44-150">Low-bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have numerous people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="9ec44-151">我們也將家長和學生的指導方針一起放在[在低頻寬時使用 Teams 來完成學校作業](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)一文內供您檢閱，如果遇到任何問題，則可以嘗試這些建議。</span><span class="sxs-lookup"><span data-stu-id="9ec44-151">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>