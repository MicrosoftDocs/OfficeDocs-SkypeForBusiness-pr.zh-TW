---
title: Lync Server 2013： 規劃遠端通話控制
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
ms.openlocfilehash: 35b8586df49eb1dd7a10e94d3231cc2fdc082353
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="e1d3b-102">規劃 Lync Server 2013 中的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e1d3b-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1d3b-103">_**主題上次修改日期：** 2012年-09-05_</span><span class="sxs-lookup"><span data-stu-id="e1d3b-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="e1d3b-104">在 [Lync Server 2013 支援遠端呼叫控制案例可讓使用者在其桌面的電腦上使用 Lync 2013 控制其專用交換機 (pbx) 電話。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="e1d3b-105">本節說明遠端呼叫控制功能，以及部署遠端呼叫控制的需求。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="e1d3b-106">PBX 與 Lync Server 2013 之間的整合可讓使用者啟用遠端呼叫控制，可使用 Lync 2013 使用者介面 (UI) 以下列方式控制 PBX 電話上的通話：</span><span class="sxs-lookup"><span data-stu-id="e1d3b-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1d3b-107">最終，主控使用者之 PBX 電話的 PBX 功能可決定該使用者可使用的遠端呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="e1d3b-108">撥出電話</span><span class="sxs-lookup"><span data-stu-id="e1d3b-108">Make an outgoing call</span></span>

  - <span data-ttu-id="e1d3b-109">接聽來電</span><span class="sxs-lookup"><span data-stu-id="e1d3b-109">Answer an incoming call</span></span>

  - <span data-ttu-id="e1d3b-110">使用立即訊息接聽來電</span><span class="sxs-lookup"><span data-stu-id="e1d3b-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e1d3b-111">也就是說，當來電者的電話號碼可以是貴組織的全域通訊清單 (GAL)、 在受話者的 Lync 連絡人清單中，或同盟的協力廠商組織中的立即訊息位址相關聯。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="e1d3b-112">轉接電話</span><span class="sxs-lookup"><span data-stu-id="e1d3b-112">Transfer a call</span></span>

  - <span data-ttu-id="e1d3b-113">轉接來電</span><span class="sxs-lookup"><span data-stu-id="e1d3b-113">Forward an incoming call</span></span>

  - <span data-ttu-id="e1d3b-114">保留通話</span><span class="sxs-lookup"><span data-stu-id="e1d3b-114">Place calls on hold</span></span>

  - <span data-ttu-id="e1d3b-115">切換多個並行通話</span><span class="sxs-lookup"><span data-stu-id="e1d3b-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="e1d3b-116">在通話時接聽第二個通話 (即插撥)</span><span class="sxs-lookup"><span data-stu-id="e1d3b-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="e1d3b-117">撥打複頻式訊號 (DTMF) 數字</span><span class="sxs-lookup"><span data-stu-id="e1d3b-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="e1d3b-118">在 [交談] 視窗中，於 Microsoft Office OneNote 筆記記錄程式中輸入記事</span><span class="sxs-lookup"><span data-stu-id="e1d3b-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="e1d3b-119">此外，當使用者啟用遠端呼叫控制，Lync 2013 提供使用者，並將下列通話資訊：</span><span class="sxs-lookup"><span data-stu-id="e1d3b-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="e1d3b-120">識別來電者依名稱當來電者的電話號碼存在於 [連絡人] 清單的遠端呼叫控制功能之使用者的 Microsoft Office Outlook 訊息和共同作業用戶端、 Lync 連絡人] 清單中或貴組織的 GAL。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="e1d3b-121">過去的來電及撥出電話 (儲存至 Outlook 的 [交談記錄] 資料夾中)。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="e1d3b-122">未接來電通知傳送給使用者的 Outlook 收件匣] 資料夾，但是 Lync 正在執行時接收到來電時，才會產生。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="e1d3b-123">遠端呼叫控制及　Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e1d3b-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="e1d3b-124">雖然遠端呼叫控制功能是分開 Enterprise Voice 功能，且使用者無法啟用兩者皆適用，Enterprise Voice 會提供功能也可設定已啟用遠端呼叫控制使用者的子集。</span><span class="sxs-lookup"><span data-stu-id="e1d3b-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="e1d3b-125">如果部署企業語音時，已啟用遠端呼叫控制使用者可以使用 Lync 來存取下列 Enterprise Voice 功能：</span><span class="sxs-lookup"><span data-stu-id="e1d3b-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="e1d3b-126">撥打及接聽另一個 Lync 用戶端的音訊通話</span><span class="sxs-lookup"><span data-stu-id="e1d3b-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="e1d3b-127">加入啟用 Enterprise voice 使用者所建立會議的音訊部分</span><span class="sxs-lookup"><span data-stu-id="e1d3b-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e1d3b-128">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e1d3b-128">In This Section</span></span>

  - [<span data-ttu-id="e1d3b-129">Lync Server 2013 中的遠端呼叫控制的部署工作</span><span class="sxs-lookup"><span data-stu-id="e1d3b-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

