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
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="b2810-102">Lync Server 2013 中的大型會議排程流程</span><span class="sxs-lookup"><span data-stu-id="b2810-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2810-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b2810-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b2810-104">因為在專門大型的會議池中只支援一支大型會議，我們建議您實施大型會議排程程式來協助避免大型會議的衝突。</span><span class="sxs-lookup"><span data-stu-id="b2810-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="b2810-105">此排程程式的目的是協助您設定大型會議。</span><span class="sxs-lookup"><span data-stu-id="b2810-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="b2810-106">Lync Server 或 Lync Server 用戶端不會直接提供此類功能。</span><span class="sxs-lookup"><span data-stu-id="b2810-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="b2810-107">實施這類程式的其中一個方法是使用貴組織的支援小組的票證系統（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="b2810-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="b2810-108">針對大型會議召集人，排程大型會議需要完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b2810-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="b2810-109">除了簡報者清單之外，會議召集人或代理人決定近期會議的時間、持續時間及大小。</span><span class="sxs-lookup"><span data-stu-id="b2810-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="b2810-110">如果預期的會議大小超過250的使用者，或可確保會議的使用者經驗少於250個使用者，召集人或代理人會提交大型會議的要求。</span><span class="sxs-lookup"><span data-stu-id="b2810-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="b2810-111">排程員工會檢查是否有可用的要求日期和時間。</span><span class="sxs-lookup"><span data-stu-id="b2810-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="b2810-112">因為我們一次只支援專用池的單一大型會議，所以排程員工必須檢查大型會議行事曆，以判斷是否有針對要求的日期和時間排程其他會議。</span><span class="sxs-lookup"><span data-stu-id="b2810-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="b2810-113">如果有所要求的時間，員工會核准會議邀請。</span><span class="sxs-lookup"><span data-stu-id="b2810-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="b2810-114">如果要求受到核准，排程員工（在專用的池中使用認證）會使用 Lync 2013 的線上會議增益集，在專用大型會議池子上設定會議。</span><span class="sxs-lookup"><span data-stu-id="b2810-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="b2810-115">要用來加入會議的 URL 會提供給申請者，作為核准通知的一部分。</span><span class="sxs-lookup"><span data-stu-id="b2810-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="b2810-116">會議召集人或代理人會使用 Outlook 來排程即將到來的會議，新增加入會議的 URL 至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="b2810-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="b2810-117">[會議召集人] 或 [代理人] 會指定受邀的使用者，併發出會議邀請。</span><span class="sxs-lookup"><span data-stu-id="b2810-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="b2810-118">下圖說明用於排程大型會議的一般要求與核准工作流程。</span><span class="sxs-lookup"><span data-stu-id="b2810-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="b2810-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="b2810-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

