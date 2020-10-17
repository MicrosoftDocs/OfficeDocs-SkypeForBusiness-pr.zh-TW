---
title: Lync Server 2013：大型會議排程處理常式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb2de8387abb48ad67b8a39bc1ac3ffc353a9b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514010"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="62aa9-102">Lync Server 2013 中的大型會議排程處理常式</span><span class="sxs-lookup"><span data-stu-id="62aa9-102">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62aa9-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="62aa9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="62aa9-104">因為在專屬的大型會議集區上一次只支援一個大型會議，所以建議您執行大型會議排程程式，以協助避免大型會議衝突。</span><span class="sxs-lookup"><span data-stu-id="62aa9-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="62aa9-105">這類排程處理的目的是為了協助設定大型會議。</span><span class="sxs-lookup"><span data-stu-id="62aa9-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="62aa9-106">Lync Server 或 Lync Server 用戶端不會直接提供這類功能。</span><span class="sxs-lookup"><span data-stu-id="62aa9-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="62aa9-107">實施這類程式的其中一個方法是使用貴組織的支援小組的票證系統（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="62aa9-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="62aa9-108">對於大型會議的召集人，排程大型會議需要完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="62aa9-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="62aa9-109">會議召集人或代理人會決定即將召開之會議的時間、工期和大小，以及簡報者清單。</span><span class="sxs-lookup"><span data-stu-id="62aa9-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="62aa9-110">如果預期的會議大小超過250的使用者，或是為了確保會議的使用者體驗低於250的使用者，召集人或代理人會送出大型會議的要求。</span><span class="sxs-lookup"><span data-stu-id="62aa9-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="62aa9-111">排程員工會檢查是否有可用的要求日期和時間。</span><span class="sxs-lookup"><span data-stu-id="62aa9-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="62aa9-112">因為我們一次只支援專屬集區的單一大型會議，所以排程人員需要檢查大型會議行事曆，以判斷是否有針對要求的日期和時間排定的其他會議。</span><span class="sxs-lookup"><span data-stu-id="62aa9-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="62aa9-113">如果有可用的要求時間，則人員會核准會議邀請。</span><span class="sxs-lookup"><span data-stu-id="62aa9-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="62aa9-114">如果已核准要求，排程員工 (使用專用集區上的認證) 使用 Lync 2013 的線上會議增益集，以供 Outlook 在專屬的大型會議集區上設定會議。</span><span class="sxs-lookup"><span data-stu-id="62aa9-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="62aa9-115">加入會議時所使用的 URL 會提供給申請者，做為核准通知的一部分。</span><span class="sxs-lookup"><span data-stu-id="62aa9-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="62aa9-116">會議召集人或代理人會使用 Outlook 來排程即將召開的會議，新增將會議加入會議邀請的 URL。</span><span class="sxs-lookup"><span data-stu-id="62aa9-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="62aa9-117">會議召集人或代理人會指定要邀請的使用者，併發出會議邀請。</span><span class="sxs-lookup"><span data-stu-id="62aa9-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="62aa9-118">下圖說明排定大型會議的一般要求與核准工作流程。</span><span class="sxs-lookup"><span data-stu-id="62aa9-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="62aa9-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="62aa9-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

