---
title: Lync Server 2013：會議的排程詳細資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="6493c-102">Lync Server 2013 中的會議排程詳細資料</span><span class="sxs-lookup"><span data-stu-id="6493c-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6493c-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="6493c-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="6493c-104">在您檢查並確定未在要求的時間前排程任何其他會議之後，處理要求的大型會議支援人員會在大型會議泳池上排程會議。</span><span class="sxs-lookup"><span data-stu-id="6493c-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="6493c-105">使用與 Lync Server 2013 用戶端一起安裝的 Lync 線上會議增益集，在專用大型會議池中使用 Lync Server 啟用的使用者認證來執行這項工作。</span><span class="sxs-lookup"><span data-stu-id="6493c-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="6493c-106">若要確保最佳的使用者體驗，請務必按照適合會議召集人需求的正確存取層級和會議設定來排程大型會議。</span><span class="sxs-lookup"><span data-stu-id="6493c-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="6493c-107">我們建議在 Lync 會議選項中設定下列排程設定：</span><span class="sxs-lookup"><span data-stu-id="6493c-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="6493c-108">針對每個大型會議使用新的會議空間，而不是重複使用專用會議空間。</span><span class="sxs-lookup"><span data-stu-id="6493c-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="6493c-109">指定會議存取層級，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6493c-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="6493c-110">如果組織中至少有一個受邀者，請將會議存取類型設定為 **[任何人] （無限制**）。</span><span class="sxs-lookup"><span data-stu-id="6493c-110">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**.</span></span> <span data-ttu-id="6493c-111">這可讓您避免在會議進行中時，不需要管理可能較大的大廳。</span><span class="sxs-lookup"><span data-stu-id="6493c-111">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="6493c-112">如果會議是僅限內部會議，請將會議存取類型設定為 [**我的組織中的任何人**]。</span><span class="sxs-lookup"><span data-stu-id="6493c-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6493c-113">避免將 [會議存取類型] 設定為 [<STRONG>我從公司邀請的人員</STRONG>]，因為當您使用此設定時，召集人必須將所有使用者電子郵件地址新增至被邀請者清單，而且您無法邀請通訊群組。</span><span class="sxs-lookup"><span data-stu-id="6493c-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="6493c-114">避免將會議存取類型設定為<STRONG>[僅自己] （會議召集人），</STRONG>因為這項設定需要每個會議參與者（包括簡報者）都必須放在會議執行時間的大廳中。</span><span class="sxs-lookup"><span data-stu-id="6493c-114">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="6493c-115">負責執行大型會議的人員必須持續監視大廳名單並承認大廳中的新使用者。</span><span class="sxs-lookup"><span data-stu-id="6493c-115">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="6493c-116">[允許從手機撥入的使用者] 透過核取 [來電者**直接取得**] 設定來自動進入會議。</span><span class="sxs-lookup"><span data-stu-id="6493c-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="6493c-117">明確邀請下列使用者：</span><span class="sxs-lookup"><span data-stu-id="6493c-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="6493c-118">會議召集人和委派（申請者）</span><span class="sxs-lookup"><span data-stu-id="6493c-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="6493c-119">會議申請者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="6493c-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6493c-120">如果 [會議存取類型] 設定為<STRONG>[我選擇的人員</STRONG>]，您必須明確將大型會議的參與者新增為會議的被邀請者。</span><span class="sxs-lookup"><span data-stu-id="6493c-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="6493c-121">明確管理簡報者，而不是將簡報者選項設定為其中一個自動升級值。</span><span class="sxs-lookup"><span data-stu-id="6493c-121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values.</span></span> <span data-ttu-id="6493c-122">請務必將下列使用者新增為簡報者：</span><span class="sxs-lookup"><span data-stu-id="6493c-122">Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="6493c-123">會議召集人和委派（申請者）</span><span class="sxs-lookup"><span data-stu-id="6493c-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="6493c-124">大型會議申請者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="6493c-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6493c-125">透過顯式管理簡報者，您可以控制簡報者的數目，讓您可以將簡報者限制為小數位，以讓其擁有有效的大型會議。</span><span class="sxs-lookup"><span data-stu-id="6493c-125">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="6493c-126">如果大多數會議參與者都有出席者角色，這有助於減少人員不小心控制簡報的機率、刪除 PowerPoint 簡報、靜音/unmuting 簡報者，以及其他中斷會議的機會。</span><span class="sxs-lookup"><span data-stu-id="6493c-126">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="6493c-127">核取 [**所有出席者靜音**] 設定，以確保只有簡報者可以將音訊廣播到會議中。</span><span class="sxs-lookup"><span data-stu-id="6493c-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="6493c-128">核取 [**封鎖出席者的影片**] 設定，以確保只有簡報者可以將影片廣播到會議中。</span><span class="sxs-lookup"><span data-stu-id="6493c-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="6493c-129">下圖顯示適用于 Lync 之線上會議增益集的建議設定。</span><span class="sxs-lookup"><span data-stu-id="6493c-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="6493c-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="6493c-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

