---
title: Lync Server 2013： 排程會議詳細資料
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
ms.openlocfilehash: 7dd61ce47daf1898afd1fb654493ef12ebee9ff1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="aba1a-102">Lync Server 2013 中的會議排程詳細資料</span><span class="sxs-lookup"><span data-stu-id="aba1a-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aba1a-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="aba1a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="aba1a-104">在檢查確認於要求的時間沒有排程其他會議之後，處理該要求的大型會議支援人員會在大型會議集區中排程會議。</span><span class="sxs-lookup"><span data-stu-id="aba1a-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="aba1a-105">使用 Lync Server 2013 用戶端執行這項工作，以安裝使用的專用的大型會議集區中的 Lync Server 啟用的使用者認證的 Lync 線上會議增益集。</span><span class="sxs-lookup"><span data-stu-id="aba1a-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="aba1a-106">為了確保最佳使用者體驗，排程大型會議時，請務必以適合會議召集人之需求的適當存取層級及會議設定。</span><span class="sxs-lookup"><span data-stu-id="aba1a-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="aba1a-107">我們建議下列排程中的設定 Lync 會議選項：</span><span class="sxs-lookup"><span data-stu-id="aba1a-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="aba1a-108">針對每場大型會議使用新的會議空間，而非重複使用專用會議空間。</span><span class="sxs-lookup"><span data-stu-id="aba1a-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="aba1a-109">以下列方式指定會議存取層級：</span><span class="sxs-lookup"><span data-stu-id="aba1a-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="aba1a-p103">如果至少有一位組織外的受邀者，則設定會議存取類型為 **[任何人 (沒有限制)]**。這可避免您在會議進行中還需要管理或許擁擠的大廳。</span><span class="sxs-lookup"><span data-stu-id="aba1a-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="aba1a-112">如果會議是純內部會議，則設定會議存取類型為 **[來自我組織的任何人]**。</span><span class="sxs-lookup"><span data-stu-id="aba1a-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aba1a-113">避免設定會議存取類型為 <STRONG>[我公司中受邀請的人員]</STRONG>，因為使用此設定時，召集人必須將所有使用者電子郵件地址新增到受邀者清單中，而且無法邀請通訊群組。</span><span class="sxs-lookup"><span data-stu-id="aba1a-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="aba1a-p104">避免設定會議存取類型為 <STRONG>[只限會議召集人自己]</STRONG>，因為此設定需要每位會議參與者 (包括簡報者) 在會議舉行時間聚集在大廳。負責舉行該場大型會議的人員就必須時時監控大廳名冊，准許在大廳的新使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="aba1a-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="aba1a-116">核取 **[來電者可直接加入]** 設定，允許以電話撥入的使用者自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="aba1a-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="aba1a-117">明確邀請下列使用者：</span><span class="sxs-lookup"><span data-stu-id="aba1a-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="aba1a-118">會議召集人及代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="aba1a-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="aba1a-119">會議要求者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="aba1a-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aba1a-120">如果會議存取類型設定為 <STRONG>[我選擇的人員]</STRONG>，則必須將大型會議中每位參與者明確新增為會議的受邀者。</span><span class="sxs-lookup"><span data-stu-id="aba1a-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="aba1a-p105">明確管理簡報者，而非將簡報者選項設定為其中一項自動升級值。務必將下列使用者新增為簡報者：</span><span class="sxs-lookup"><span data-stu-id="aba1a-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="aba1a-123">會議召集人及代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="aba1a-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="aba1a-124">大型會議要求者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="aba1a-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aba1a-p106">透過明確管理簡報者，您可以控制簡報者的人數，限制簡報者的人數少到足以讓大型會議能有效率地舉行。如果大多數的會議參與者為出席者角色，這有助於降低以下事件的發生機會：人員意外主導簡報、刪除 PowerPoint 簡報、將簡報者靜音/取消靜音，以及其他會議干擾。</span><span class="sxs-lookup"><span data-stu-id="aba1a-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="aba1a-127">核取 **[將所有出席者設為靜音]** 設定，確保只有簡報者能在會議中廣播音訊。</span><span class="sxs-lookup"><span data-stu-id="aba1a-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="aba1a-128">核取 **[封鎖出席者的視訊]** 設定，確保只有簡報者能在會議中廣播視訊。</span><span class="sxs-lookup"><span data-stu-id="aba1a-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="aba1a-129">下圖顯示 Lync 線上會議增益集的建議的設定。</span><span class="sxs-lookup"><span data-stu-id="aba1a-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="aba1a-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="aba1a-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

