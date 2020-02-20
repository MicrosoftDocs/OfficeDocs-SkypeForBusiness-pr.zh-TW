---
title: Lync Server 2013： 大型會議排程處理序
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
ms.openlocfilehash: b83d5225982817342e6d2361099efb1ce1dcc80a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="0e565-102">Lync Server 2013 中的大型會議排程處理序</span><span class="sxs-lookup"><span data-stu-id="0e565-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e565-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="0e565-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0e565-104">因為一次只能執行一個大型會議支援的專用的大型會議集區上，我們建議您實作大型會議排程處理程序，協助防範大型會議衝突。</span><span class="sxs-lookup"><span data-stu-id="0e565-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="0e565-105">這類排程程序的目的是協助大型會議的設定。</span><span class="sxs-lookup"><span data-stu-id="0e565-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="0e565-106">這類功能不是提供直接 Lync Server 或 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="0e565-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="0e565-107">實作這類程序的一種方式是使用您的組織支援小組的票證系統中，如果有的話。</span><span class="sxs-lookup"><span data-stu-id="0e565-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="0e565-108">大型會議的召集人，排程大型會議需要完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0e565-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="0e565-109">會議召集人或委派來決定時間、 期間和即將來臨的會議，除了的簡報者清單的大小。</span><span class="sxs-lookup"><span data-stu-id="0e565-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="0e565-110">如果預期的會議大小超過 250 位使用者，或若要確保少於 250 位使用者的會議的最佳使用者經驗，召集人或委派送出大型會議要求。</span><span class="sxs-lookup"><span data-stu-id="0e565-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="0e565-111">排程的人員會檢查是否有可用的要求的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0e565-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="0e565-112">由於我們支援只有單一大型會議的專屬集區上一次，排程人員需要檢查大型會議行事曆，以判斷是否有另一個會議排程要求的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0e565-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="0e565-113">如果使用要求的時間，則人員核准會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0e565-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="0e565-114">如果核准要求，（使用專用的集區上的認證） 排程工作人員使用線上會議增益集與 Outlook 的 Lync 2013 的設定專用的大型會議集區上的會議。</span><span class="sxs-lookup"><span data-stu-id="0e565-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="0e565-115">要用來加入會議的 URL 提供給要求者的核准明的一部分。</span><span class="sxs-lookup"><span data-stu-id="0e565-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="0e565-116">會議召集人或委派使用 Outlook 來排定即將來臨的會議，新增至會議邀請中加入會議的 URL。</span><span class="sxs-lookup"><span data-stu-id="0e565-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="0e565-117">會議召集人或委派，會指定使用者的邀請，並送出的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0e565-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="0e565-118">下圖說明的一般要求與核准工作流程排程大型會議。</span><span class="sxs-lookup"><span data-stu-id="0e565-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="0e565-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="0e565-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

