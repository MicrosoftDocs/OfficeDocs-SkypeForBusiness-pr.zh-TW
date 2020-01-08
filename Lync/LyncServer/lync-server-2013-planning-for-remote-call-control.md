---
title: Lync Server 2013：規劃遠端通話控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ede2b5d63c57864f478cb8fd9bcd4689a91ab3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="b0703-102">在 Lync Server 2013 中規劃遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b0703-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0703-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="b0703-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="b0703-104">在 Lync Server 2013 中，遠端通話控制案例的支援可讓使用者在其桌上型電腦上使用 Lync 2013 控制其私人分支 exchange （PBX）電話。</span><span class="sxs-lookup"><span data-stu-id="b0703-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="b0703-105">本節說明部署遠端通話控制的遠端呼叫控制功能與需求。</span><span class="sxs-lookup"><span data-stu-id="b0703-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="b0703-106">在 PBX 和 Lync Server 2013 之間整合，可讓遠端呼叫控制的使用者使用 Lync 2013 使用者介面（UI），透過下列方式控制其 PBX 手機上的呼叫：</span><span class="sxs-lookup"><span data-stu-id="b0703-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0703-107">最終，託管使用者 PBX 手機的 PBX 功能決定該使用者可以使用的遠端呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="b0703-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="b0703-108">撥打撥出電話</span><span class="sxs-lookup"><span data-stu-id="b0703-108">Make an outgoing call</span></span>

  - <span data-ttu-id="b0703-109">接聽來電</span><span class="sxs-lookup"><span data-stu-id="b0703-109">Answer an incoming call</span></span>

  - <span data-ttu-id="b0703-110">使用立即訊息接聽來電</span><span class="sxs-lookup"><span data-stu-id="b0703-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0703-111">也就是說，當來電者的電話號碼可以與組織全域通訊清單（GAL）中的立即訊息位址相關聯，請在被叫方的 Lync 連絡人清單中，或在聯盟夥伴的組織中。</span><span class="sxs-lookup"><span data-stu-id="b0703-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="b0703-112">轉接來電</span><span class="sxs-lookup"><span data-stu-id="b0703-112">Transfer a call</span></span>

  - <span data-ttu-id="b0703-113">轉接來電</span><span class="sxs-lookup"><span data-stu-id="b0703-113">Forward an incoming call</span></span>

  - <span data-ttu-id="b0703-114">保留通話</span><span class="sxs-lookup"><span data-stu-id="b0703-114">Place calls on hold</span></span>

  - <span data-ttu-id="b0703-115">在多個併發通話間切換</span><span class="sxs-lookup"><span data-stu-id="b0703-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="b0703-116">接聽通話中的第二個通話（也就是通話等待）</span><span class="sxs-lookup"><span data-stu-id="b0703-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="b0703-117">撥號雙音調 multifrequency （DTMF）位數</span><span class="sxs-lookup"><span data-stu-id="b0703-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="b0703-118">在交談視窗中，在 Microsoft Office OneNote 筆記記錄程式中輸入記事</span><span class="sxs-lookup"><span data-stu-id="b0703-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="b0703-119">此外，當使用者啟用 [遠端通話控制] 時，Lync 2013 會為使用者提供下列通話資訊：</span><span class="sxs-lookup"><span data-stu-id="b0703-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="b0703-120">來電者的電話號碼在遠端呼叫控制啟用使用者的 Microsoft Office Outlook [訊息與共同作業用戶端]、[Lync 連絡人清單] 或貴組織的 GAL 中的 [連絡人] 清單中存在的名稱。</span><span class="sxs-lookup"><span data-stu-id="b0703-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="b0703-121">過去的撥入和撥出通話，會儲存在 Outlook 中的 [交談記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b0703-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="b0703-122">未接來電通知會傳送到使用者的 Outlook [收件匣] 資料夾，但只有在收到來電時，才會產生 Lync。</span><span class="sxs-lookup"><span data-stu-id="b0703-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="b0703-123">遠端通話控制和企業語音</span><span class="sxs-lookup"><span data-stu-id="b0703-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="b0703-124">雖然遠端通話控制功能是與企業語音功能分開的，而且不能同時為使用者啟用，但企業語音也提供可供啟用遠端呼叫控制的使用者使用的功能子集。</span><span class="sxs-lookup"><span data-stu-id="b0703-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="b0703-125">如果已部署企業語音，則已啟用遠端通話控制的使用者可以使用 Lync 來存取下列企業語音功能：</span><span class="sxs-lookup"><span data-stu-id="b0703-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="b0703-126">撥打及接聽其他 Lync 用戶端的語音通話</span><span class="sxs-lookup"><span data-stu-id="b0703-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="b0703-127">加入由啟用企業語音的使用者所建立之會議的音訊部分</span><span class="sxs-lookup"><span data-stu-id="b0703-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b0703-128">本節內容</span><span class="sxs-lookup"><span data-stu-id="b0703-128">In This Section</span></span>

  - [<span data-ttu-id="b0703-129">Lync Server 2013 中遠端呼叫控制的部署工作</span><span class="sxs-lookup"><span data-stu-id="b0703-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

