---
title: Lync Server 2013 電話撥入式會議概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="cc8b0-102">Lync Server 2013 中的電話撥入式會議概述</span><span class="sxs-lookup"><span data-stu-id="cc8b0-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc8b0-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="cc8b0-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="cc8b0-104">如果您的組織擁有的使用者需要在不在辦公室或無法存取電腦的情況下，出席 Lync Server 2013 內部部署會議，則可以部署電話撥入式會議，讓他們可以使用公開的交換電話加入會議網路（PSTN）電話。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="cc8b0-105">電話撥入式會議是您可以在部署 Lync Server 2013 會議時設定的選擇性功能。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="cc8b0-106">雖然電話撥入式會議使用的是企業語音用途的一些相同的 Lync Server 2013 元件，但是您可以部署電話撥入式會議，即使您沒有部署企業語音也一樣。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc8b0-107">如果您要部署電話撥入式會議，您必須在部署 Lync Server 2013 會議的每個池中部署它。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="cc8b0-108">您不需要在每個池中指派存取號碼，但您必須在每個池中部署撥入功能。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="cc8b0-109">當使用者從某個池中呼叫存取號碼以在不同的池中加入 Lync Server 2013 會議時，此需求支援所記錄的名稱功能。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="cc8b0-110">會議必須在會議原則中啟用撥入存取。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="cc8b0-111">根據預設，啟用撥入存取的會議在會議邀請中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="cc8b0-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="cc8b0-112">識別會議的數位會議 ID。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="cc8b0-113">一或多個 PSTN 存取號碼。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="cc8b0-114">[電話撥入式會議設定] 頁面的連結，其中包含其相關語言的完整存取號碼清單;建立、重設或解除封鎖個人身分識別號碼（Pin）的位置;以及其他資訊，例如雙音調多重頻率（DTMF）控制。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="cc8b0-115">電話撥入式會議支援企業和匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="cc8b0-116">企業使用者在其組織內擁有 Active Directory 網域服務認證和 Lync Server 2013 帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="cc8b0-117">匿名使用者沒有貴組織內的企業認證。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="cc8b0-118">在電話撥入式會議的內容中，聯盟夥伴組織中使用 PSTN 連接至會議的使用者，會被視為匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="cc8b0-119">對於電話撥入式會議，與其他內容不同，聯盟使用者不會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="cc8b0-120">加入已啟用電話撥入存取的會議的企業使用者或會議領導者，請撥打電話給其中一個會議存取號碼，然後系統會提示您輸入會議 ID。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="cc8b0-121">如果領導者尚未加入會議，使用者可以輸入其整合通訊（UC）延伸（或完整的電話號碼），並釘選給領導，或等候接受者承認。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="cc8b0-122">會議召集人只需輸入 PIN，就可以將會議加入為主持人。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="cc8b0-123">前端伺服器使用完整的電話號碼或分機，以及 PIN 的組合，以唯一的方式將企業使用者對應至其 Active Directory 認證。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="cc8b0-124">因此，企業使用者是透過會議中的名稱進行驗證及識別。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="cc8b0-125">企業使用者也可以假設由召集人預先定義的會議角色。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc8b0-126">從 office IP 手機或 Lync Server 2013 或 Lync 2010 應答撥入的企業使用者，不會因已驗證，而提示他們輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="cc8b0-127">想要加入電話撥入式會議的匿名使用者撥打電話給其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-127">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID.</span></span> <span data-ttu-id="cc8b0-128">未經驗證的匿名使用者也會收到記錄其名稱的提示。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-128">Unauthenticated anonymous users are also prompted to record their name.</span></span> <span data-ttu-id="cc8b0-129">所記錄的名稱會識別會議中未經驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-129">The recorded name identifies unauthenticated users in the conference.</span></span> <span data-ttu-id="cc8b0-130">除非至少有一個領導或經過驗證的使用者已加入，且無法指派預先定義的角色，否則匿名使用者將無法獲准參與會議。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-130">Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc8b0-131">選擇不輸入其電話號碼和 PIN 的企業使用者未經過驗證。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-131">Enterprise users who choose not to enter their phone number and PIN are not authenticated.</span></span> <span data-ttu-id="cc8b0-132">系統會提示他們記錄其名稱，並在會議中被視為匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-132">They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="cc8b0-133">在排程時間，會議召集人可以選擇將會議設為關閉或鎖定，以限制會議的存取權。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="cc8b0-134">在這種情況下，系統會要求撥入使用者進行驗證。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="cc8b0-135">如果撥入使用者失敗，或選擇不進行驗證，就會將它們傳輸到大廳。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="cc8b0-136">它們會在大廳等候，直到前置字元接受或拒絕，或者它們結束並中斷連接。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="cc8b0-137">如果電話撥入的使用者正在等待會議，請聆聽音樂。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="cc8b0-138">在他們獲准加入會議之後，撥入使用者可以參與會議的音訊部分，而且可以使用電話鍵台來行使雙音多頻率（DTMF）命令。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="cc8b0-139">[撥入前置字元] 可以行使 DTMF 命令，以將參與者的開啟或關閉、鎖定或解除鎖定，以及開啟或關閉公告的功能。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="cc8b0-140">前置字元也可以使用 DTMF 命令，讓所有人都能透過它來變更會議的許可權，以允許後續加入的任何人。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="cc8b0-141">所有撥入參與者都可以行使 DTMF 命令來聽取說明、聆聽會議名單並將自己設為靜音。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="cc8b0-142">撥入參與者（無論是從 PSTN 撥號），在會議期間聆聽個人宣告（例如是否已靜音或已取消靜音），或是現正播放會議，或是有人正在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc8b0-143">若參與者是透過按一下連結而不是撥號來加入會議，請勿聽到個人公告。</span><span class="sxs-lookup"><span data-stu-id="cc8b0-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

