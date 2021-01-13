---
title: 商務用 Skype Server 中的會議詳細資料包告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 摘要：瞭解在商務用 Skype Server 中使用的會議詳細資料包告。
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816903"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="a4d4f-103">商務用 Skype Server 中的會議詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="a4d4f-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="a4d4f-104">**摘要：** 深入瞭解商務用 Skype Server 中所用的會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="a4d4f-p101">「會議詳細資料報告」可提供參與會議之使用者的詳細資訊。例如，您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間，以及用來將使用者與會議連線的端點使用者代理程式之類的資訊。您也可以查看使用者在每個會議中的角色 (例如，簡報者或是出席者)。更重要的是，您可以更快速地查看哪些使用者已順利加入並完成會議，而哪些使用者無法順利加入並完成會議。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="a4d4f-109">存取會議詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="a4d4f-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="a4d4f-110">您可從下列報告來存取會議詳細資料報告：</span><span class="sxs-lookup"><span data-stu-id="a4d4f-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="a4d4f-111">[Call Admission Control Report](call-admission-control-report.md) (按一下會議的 [詳細資料] 計量)</span><span class="sxs-lookup"><span data-stu-id="a4d4f-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="a4d4f-112">[Failure List Report](failure-list-report.md) (按一下 [會議] 計量)</span><span class="sxs-lookup"><span data-stu-id="a4d4f-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="a4d4f-113">[User Activity Report](call-diagnostic-reports-per-user.md) (按一下 [會議 URI] 計量)</span><span class="sxs-lookup"><span data-stu-id="a4d4f-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="a4d4f-114">您還可從會議詳細資料報告中，按一下 [診斷報告] ([詳細資料]) 計量，來存取[Diagnostic Report](diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="a4d4f-115">篩選</span><span class="sxs-lookup"><span data-stu-id="a4d4f-115">Filters</span></span>

<span data-ttu-id="a4d4f-p102">無。您無法篩選會議詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="a4d4f-118">指標</span><span class="sxs-lookup"><span data-stu-id="a4d4f-118">Metrics</span></span>

<span data-ttu-id="a4d4f-119">下表列出會議詳細資料報告的「會議資訊」區段中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="a4d4f-120">**會議資訊計量**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="a4d4f-121">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-121">**Name**</span></span>                 | <span data-ttu-id="a4d4f-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a4d4f-123">**會議 URI**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="a4d4f-p103">指派給會議的 URI。例如：</span><span class="sxs-lookup"><span data-stu-id="a4d4f-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="a4d4f-126">sip： kmyer@litwareinc .com; gruu; 不透明 = 應用程式：會議： focus：識別碼： drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="a4d4f-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="a4d4f-127">**集區 FQDN**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="a4d4f-128">工作階段所涉及的登錄器集區或 Edge Server 的完整網域名稱。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="a4d4f-129">**開始時間**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-129">**Start time**</span></span> <br/>     | <span data-ttu-id="a4d4f-130">會議開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="a4d4f-131">**召集人**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="a4d4f-132">召開會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="a4d4f-133">**結束時間**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-133">**End time**</span></span> <br/>       | <span data-ttu-id="a4d4f-134">會議結束的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="a4d4f-135">下表列出會議詳細資料報告的「會議參與區段」中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="a4d4f-136">**會議參與計量**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="a4d4f-137">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-137">**Name**</span></span>|<span data-ttu-id="a4d4f-138">**描述**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4d4f-139">**使用者**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-139">**User**</span></span> <br/> |<span data-ttu-id="a4d4f-140">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-141">**Role**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-141">**Role**</span></span> <br/> |<span data-ttu-id="a4d4f-142">會議參與者所扮演的角色 (例如，簡報者)。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-143">**連線能力**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="a4d4f-144">參與者的網路連線 (一般來說是從內部或從外部)。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-145">**加入時間**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-145">**Join time**</span></span> <br/> |<span data-ttu-id="a4d4f-146">參與者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-147">**離開時間**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-147">**Leave time**</span></span> <br/> |<span data-ttu-id="a4d4f-148">參與者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-149">**使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-149">**User agent**</span></span> <br/> |<span data-ttu-id="a4d4f-150">參與者的端點所使用的軟體識別碼。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-151">**診斷報告**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="a4d4f-p104">可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="a4d4f-154">下表列出會議詳細資料包告之 [會議形式] 區段中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="a4d4f-155">**會議形式計量**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="a4d4f-156">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-156">**Name**</span></span>|<span data-ttu-id="a4d4f-157">**描述**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4d4f-158">**使用者**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-158">**User**</span></span> <br/> |<span data-ttu-id="a4d4f-159">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-160">**加入時間**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-160">**Join time**</span></span> <br/> |<span data-ttu-id="a4d4f-161">參與者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-162">**離開時間**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-162">**Leave time**</span></span> <br/> |<span data-ttu-id="a4d4f-163">參與者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-164">**會議伺服器 URI**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="a4d4f-165">會議中所使用之會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="a4d4f-166">**診斷報告**</span><span class="sxs-lookup"><span data-stu-id="a4d4f-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="a4d4f-p105">可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="a4d4f-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


