---
title: 商務用 Skype Server 中的會議詳細資料包表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '摘要: 瞭解商務用 Skype Server 中使用的會議詳細資料包表。'
ms.openlocfilehash: 17337624c955dfa174f7b98772fdd836e82891d0
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271391"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="596f7-103">商務用 Skype Server 中的會議詳細資料包表</span><span class="sxs-lookup"><span data-stu-id="596f7-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="596f7-104">**摘要:** 瞭解商務用 Skype Server 中所用的會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="596f7-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="596f7-105">[會議詳細資料] 報告提供參與會議之所有使用者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="596f7-105">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="596f7-106">例如, 您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間, 以及用來將該使用者連線到會議的端點使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="596f7-106">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="596f7-107">您也可以在每個會議中查看使用者角色的資訊 (例如, 簡報者或出席者)。</span><span class="sxs-lookup"><span data-stu-id="596f7-107">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="596f7-108">最重要的是, 您會快速看到哪些使用者成功加入並完成會議, 哪些使用者無法順利加入並完成會議。</span><span class="sxs-lookup"><span data-stu-id="596f7-108">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="596f7-109">存取會議詳細資料包表</span><span class="sxs-lookup"><span data-stu-id="596f7-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="596f7-110">您可以從下列報表存取會議詳細資料包告:</span><span class="sxs-lookup"><span data-stu-id="596f7-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="596f7-111">[[通話許可控制] 報告](call-admission-control-report.md)(按一下會議的詳細指標)</span><span class="sxs-lookup"><span data-stu-id="596f7-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="596f7-112">[[失敗清單] 報告](failure-list-report.md)(按一下會議規格)</span><span class="sxs-lookup"><span data-stu-id="596f7-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="596f7-113">[使用者活動報告](call-diagnostic-reports-per-user.md)(按一下會議 URI 躍點數)</span><span class="sxs-lookup"><span data-stu-id="596f7-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="596f7-114">從會議詳細資料包告中, 您可以按一下診斷報告 (詳細資料) 度量來存取[診斷報告](diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="596f7-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="596f7-115">濾鏡</span><span class="sxs-lookup"><span data-stu-id="596f7-115">Filters</span></span>

<span data-ttu-id="596f7-116">無。</span><span class="sxs-lookup"><span data-stu-id="596f7-116">None.</span></span> <span data-ttu-id="596f7-117">您無法在會議詳細資料包表中篩選。</span><span class="sxs-lookup"><span data-stu-id="596f7-117">You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="596f7-118">指標</span><span class="sxs-lookup"><span data-stu-id="596f7-118">Metrics</span></span>

<span data-ttu-id="596f7-119">下表列出在會議詳細資料包表的 [會議資訊] 區段中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="596f7-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="596f7-120">**會議資訊度量單位**</span><span class="sxs-lookup"><span data-stu-id="596f7-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="596f7-121">**名稱**</span><span class="sxs-lookup"><span data-stu-id="596f7-121">**Name**</span></span>                 | <span data-ttu-id="596f7-122">**說明**</span><span class="sxs-lookup"><span data-stu-id="596f7-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="596f7-123">**會議 URI**</span><span class="sxs-lookup"><span data-stu-id="596f7-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="596f7-124">指派給會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="596f7-124">URI assigned to the conference.</span></span> <span data-ttu-id="596f7-125">例如：</span><span class="sxs-lookup"><span data-stu-id="596f7-125">For example:</span></span>  <br/> <span data-ttu-id="596f7-126">sip: kmyer@litwareinc.com; gruu; 不透明 = 應用程式: 會議: 焦點: id: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="596f7-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="596f7-127">**池 FQDN**</span><span class="sxs-lookup"><span data-stu-id="596f7-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="596f7-128">會話中所涉及的註冊機構池或邊緣伺服器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="596f7-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="596f7-129">**開始時間**</span><span class="sxs-lookup"><span data-stu-id="596f7-129">**Start time**</span></span> <br/>     | <span data-ttu-id="596f7-130">會議開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="596f7-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="596f7-131">**召集人**</span><span class="sxs-lookup"><span data-stu-id="596f7-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="596f7-132">組織會議的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="596f7-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="596f7-133">**結束時間**</span><span class="sxs-lookup"><span data-stu-id="596f7-133">**End time**</span></span> <br/>       | <span data-ttu-id="596f7-134">會議結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="596f7-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="596f7-135">下表列出會議詳細資料包表之會議參與區段中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="596f7-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="596f7-136">**會議參與指標**</span><span class="sxs-lookup"><span data-stu-id="596f7-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="596f7-137">**名稱**</span><span class="sxs-lookup"><span data-stu-id="596f7-137">**Name**</span></span>|<span data-ttu-id="596f7-138">**說明**</span><span class="sxs-lookup"><span data-stu-id="596f7-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="596f7-139">**使用者名**</span><span class="sxs-lookup"><span data-stu-id="596f7-139">**User**</span></span> <br/> |<span data-ttu-id="596f7-140">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="596f7-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="596f7-141">**角色**</span><span class="sxs-lookup"><span data-stu-id="596f7-141">**Role**</span></span> <br/> |<span data-ttu-id="596f7-142">會議參與者所扮演的角色 (例如, 簡報者)。</span><span class="sxs-lookup"><span data-stu-id="596f7-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="596f7-143">**連通**</span><span class="sxs-lookup"><span data-stu-id="596f7-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="596f7-144">參與者的網路連線 (通常是內部或外部的網路連線)。</span><span class="sxs-lookup"><span data-stu-id="596f7-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="596f7-145">**加入時間**</span><span class="sxs-lookup"><span data-stu-id="596f7-145">**Join time**</span></span> <br/> |<span data-ttu-id="596f7-146">參與者加入會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="596f7-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="596f7-147">**休假時間**</span><span class="sxs-lookup"><span data-stu-id="596f7-147">**Leave time**</span></span> <br/> |<span data-ttu-id="596f7-148">參與者離開會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="596f7-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="596f7-149">**使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="596f7-149">**User agent**</span></span> <br/> |<span data-ttu-id="596f7-150">參與者終點所使用之軟體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="596f7-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="596f7-151">**診斷報告**</span><span class="sxs-lookup"><span data-stu-id="596f7-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="596f7-152">提供診斷及疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="596f7-152">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="596f7-153">包括 SIP 回應代碼、診斷標頭、會議加入時間, 以及失敗會話的診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="596f7-153">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="596f7-154">下表列出在會議詳細資料包表的 [會議形式] 區段中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="596f7-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="596f7-155">**會議形式度量單位**</span><span class="sxs-lookup"><span data-stu-id="596f7-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="596f7-156">**名稱**</span><span class="sxs-lookup"><span data-stu-id="596f7-156">**Name**</span></span>|<span data-ttu-id="596f7-157">**說明**</span><span class="sxs-lookup"><span data-stu-id="596f7-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="596f7-158">**使用者名**</span><span class="sxs-lookup"><span data-stu-id="596f7-158">**User**</span></span> <br/> |<span data-ttu-id="596f7-159">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="596f7-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="596f7-160">**加入時間**</span><span class="sxs-lookup"><span data-stu-id="596f7-160">**Join time**</span></span> <br/> |<span data-ttu-id="596f7-161">參與者加入會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="596f7-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="596f7-162">**休假時間**</span><span class="sxs-lookup"><span data-stu-id="596f7-162">**Leave time**</span></span> <br/> |<span data-ttu-id="596f7-163">參與者離開會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="596f7-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="596f7-164">**會議服務器 URI**</span><span class="sxs-lookup"><span data-stu-id="596f7-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="596f7-165">在會議中使用的會議服務器 URI。</span><span class="sxs-lookup"><span data-stu-id="596f7-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="596f7-166">**診斷報告**</span><span class="sxs-lookup"><span data-stu-id="596f7-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="596f7-167">提供診斷及疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="596f7-167">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="596f7-168">包括 SIP 回應代碼、診斷標頭、會議加入時間, 以及失敗會話的診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="596f7-168">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


