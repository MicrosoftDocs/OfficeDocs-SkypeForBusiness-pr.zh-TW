---
title: Lync Server 2013：規劃遠端呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99cf4d98f02554e7de344ded843b60406e755a3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526450"
---
# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="4f6c1-102">在 Lync Server 2013 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="4f6c1-102">Planning for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f6c1-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="4f6c1-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="4f6c1-104">在 Lync Server 2013 中，支援遠端呼叫控制案例，可讓使用者在其桌上型電腦上使用 Lync 2013 來控制其專用的分支 exchange (PBX) 電話。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="4f6c1-105">本節說明遠端呼叫控制功能，以及部署遠端呼叫控制的需求。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="4f6c1-106">PBX 和 Lync Server 2013 之間的整合，可讓啟用遠端呼叫控制的使用者使用 Lync 2013 使用者介面 (UI) 以下列方式控制 PBX 電話上的通話：</span><span class="sxs-lookup"><span data-stu-id="4f6c1-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f6c1-107">最終，主控使用者之 PBX 電話的 PBX 功能可決定該使用者可使用的遠端呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="4f6c1-108">撥出電話</span><span class="sxs-lookup"><span data-stu-id="4f6c1-108">Make an outgoing call</span></span>

  - <span data-ttu-id="4f6c1-109">接聽來電</span><span class="sxs-lookup"><span data-stu-id="4f6c1-109">Answer an incoming call</span></span>

  - <span data-ttu-id="4f6c1-110">使用立即訊息接聽來電</span><span class="sxs-lookup"><span data-stu-id="4f6c1-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f6c1-111">亦即，當來電者的電話號碼可以與您組織的全域通訊清單中的立即訊息位址相關聯 (GAL) 、被叫用的 Lync 連絡人清單，或同盟協力廠商的組織中。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="4f6c1-112">轉接電話</span><span class="sxs-lookup"><span data-stu-id="4f6c1-112">Transfer a call</span></span>

  - <span data-ttu-id="4f6c1-113">轉接來電</span><span class="sxs-lookup"><span data-stu-id="4f6c1-113">Forward an incoming call</span></span>

  - <span data-ttu-id="4f6c1-114">保留通話</span><span class="sxs-lookup"><span data-stu-id="4f6c1-114">Place calls on hold</span></span>

  - <span data-ttu-id="4f6c1-115">切換多個並行通話</span><span class="sxs-lookup"><span data-stu-id="4f6c1-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="4f6c1-116">在通話時接聽第二個通話 (即插撥)</span><span class="sxs-lookup"><span data-stu-id="4f6c1-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="4f6c1-117">撥打複頻式訊號 (DTMF) 數字</span><span class="sxs-lookup"><span data-stu-id="4f6c1-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="4f6c1-118">在 [交談] 視窗中，於 Microsoft Office OneNote 筆記記錄程式中輸入記事</span><span class="sxs-lookup"><span data-stu-id="4f6c1-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="4f6c1-119">此外，當使用者啟用遠端呼叫控制時，Lync 2013 會為使用者提供下列呼叫資訊：</span><span class="sxs-lookup"><span data-stu-id="4f6c1-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="4f6c1-120">來電者的電話號碼存在於啟用遠端呼叫控制功能之使用者的 Microsoft Office Outlook 郵件和共同作業用戶端、Lync 連絡人清單或您組織的 GAL 中的連絡人清單中時，會以名稱識別來電者。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="4f6c1-121">過去的來電及撥出電話 (儲存至 Outlook 的 [交談記錄] 資料夾中)。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="4f6c1-122">未接來電通知，它會傳送至使用者的 Outlook [收件匣] 資料夾，但只有在接收來電時，才會產生 Lync。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="4f6c1-123">遠端呼叫控制及　Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="4f6c1-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="4f6c1-124">雖然遠端呼叫控制功能與 Enterprise Voice 功能不同，而且不能同時啟用使用者，但 Enterprise Voice 提供的功能子集也可供啟用遠端呼叫控制的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="4f6c1-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="4f6c1-125">如果部署了 Enterprise Voice，已啟用遠端呼叫控制的使用者可以使用 Lync 來存取下列 Enterprise Voice 功能：</span><span class="sxs-lookup"><span data-stu-id="4f6c1-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="4f6c1-126">撥打和接收其他 Lync 用戶端的音訊通話</span><span class="sxs-lookup"><span data-stu-id="4f6c1-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="4f6c1-127">加入由已啟用 Enterprise Voice 之使用者所建立之會議的音訊部分</span><span class="sxs-lookup"><span data-stu-id="4f6c1-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4f6c1-128">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4f6c1-128">In This Section</span></span>

  - [<span data-ttu-id="4f6c1-129">Lync Server 2013 中遠端呼叫控制的部署工作</span><span class="sxs-lookup"><span data-stu-id="4f6c1-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

