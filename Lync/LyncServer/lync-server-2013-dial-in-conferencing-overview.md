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
ms.openlocfilehash: d91c455c1e4bfbb2b4fe7af827265a789c9ace68
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498930"
---
# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="e8a3e-102">Lync Server 2013 中的電話撥入式會議概述</span><span class="sxs-lookup"><span data-stu-id="e8a3e-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8a3e-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="e8a3e-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="e8a3e-104">如果您的組織擁有的使用者需要在外出時參加 Lync Server 2013 內部部署會議，或沒有電腦的存取權，您可以部署電話撥入式會議，讓他們可以使用公用交換電話網路 (PSTN) 電話，加入會議。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="e8a3e-105">電話撥入式會議是一種選用的功能，您可以在部署 Lync Server 2013 會議時加以設定。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="e8a3e-106">雖然撥入式會議使用 Enterprise Voice 所用的部分相同 Lync Server 2013 元件，但即使您不部署企業語音，也可以部署電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8a3e-107">如果您部署電話撥入式會議，則必須在每個部署 Lync Server 2013 會議的集區中部署它。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="e8a3e-108">您不需要在每個集區中指派存取號碼，但是必須在每個集區中部署撥入功能。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="e8a3e-109">當使用者呼叫一個集區中的存取號碼，以在不同的集區加入 Lync Server 2013 會議時，此需求即支援記錄的名稱功能。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="e8a3e-p103">您必須在會議原則中啟用會議的撥入存取。根據預設，啟用撥入功能的會議會在會議邀請中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e8a3e-p103">Conferences must be enabled for dial-in access in meeting policy. By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="e8a3e-112">可識別會議的數值會議 ID</span><span class="sxs-lookup"><span data-stu-id="e8a3e-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="e8a3e-113">一個或多個 PSTN 存取號碼。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="e8a3e-114">[電話撥入式會議設定] 頁面的連結，其中包含其相關語言的完整存取號碼清單。用來建立、重設或解除封鎖個人識別碼 (Pin 碼的位置) ;和其他資訊，例如雙音調多重頻率 (DTMF) 控制項。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="e8a3e-115">電話撥入式會議同時支援企業和匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="e8a3e-116">企業使用者在其組織內有 Active Directory 網域服務認證和 Lync Server 2013 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="e8a3e-117">匿名使用者在您組織內沒有企業認證。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="e8a3e-118">在電話撥入式會議環境中，如果同盟協力廠商組織中的使用者使用 PSTN 連線至會議，則會視為匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="e8a3e-119">與其他環境不同，電話撥入式會議並不會驗證同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="e8a3e-120">企業使用者或會議主席欲參加已啟用撥入存取功能的會議時，要撥打其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="e8a3e-121">如果主席尚未加入會議，使用者可以輸入整合通訊 (UC) 分機 (或完整電話號碼) 和 PIN，或是等待主席准許加入會議。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="e8a3e-122">會議召集人只要輸入 PIN 即可以主席身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="e8a3e-123">前端伺服器會使用完整的電話號碼或分機和 PIN 碼的組合，將企業使用者唯一對應到其 Active Directory 認證。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="e8a3e-124">因此，在會議中，企業使用者已通過驗證，而且是以名稱識別。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="e8a3e-125">企業使用者也可以擔任由召集人所預先定義的會議角色。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8a3e-126">從 office IP 電話撥入或從 Lync Server 2013 或 Lync 2010 應答的企業使用者，不會提示他們輸入他們的電話號碼，因為這些使用者已驗證。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="e8a3e-p106">匿名使用者欲加入電話撥入式會議時，要撥打其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。未經驗證的匿名使用者還會收到提示來記錄其名稱。記錄的名稱可識別會議中未經驗證的使用者。匿名使用者要等到至少有一位主席或已驗證使用者加入會議後，才能加入會議；此外，不能指派預先定義的角色給匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8a3e-p107">選擇不輸入電話號碼及 PIN 的企業使用者不會進行驗證。他們會收到提示，表示系統將記錄其名稱，並將其視為會議中的匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="e8a3e-p108">在排程階段，會議召集人可以選擇藉由關閉或鎖定會議，以限制會議的存取。在此情況下，系統會要求撥入式使用者接受驗證。如果撥入使用者驗證失敗或選擇不接受驗證，就會移轉至大廳，在那裡等候主席接受或拒絕他們加入會議，或是等候到逾時並中斷連線為止。撥入式使用者在等待獲准加入會議時，會聽到音樂聲。撥入式使用者在獲准加入會議之後，可以參與會議的音訊部分，並且可以利用電話鍵盤來執行複頻式訊號 (DTMF) 命令。撥入式主席可以執行 DTMF 命令來開啟或關閉參與者解除靜音的能力、鎖定或解除鎖定會議、准許大廳中的人員加入會議，以及開啟或關閉進入和退出宣告。主席也可以使用 DTMF 命令來准許大廳中的所有人員加入會議，這樣會變更會議的權限，允許任何人在後來加入。所有撥入式參與者都可以執行 DTMF 命令來聽取說明、聽取會議名冊，以及將自己靜音。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-p108">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked. In this case, dial-in users are requested to authenticate. If dial-in users fail or choose not to authenticate, they are transferred to the lobby. They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected. Dial-in users hear music if they are waiting to be admitted to the conference. After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad. Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off. Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins. All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="e8a3e-142">撥入式參與者 (不管他們是不是從 PSTN 撥入) 在會議期間會聽到個人宣告 (例如他們是否被靜音或解除靜音、已在錄製會議，或是有人在大廳等候)。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8a3e-143">透過按下連結 (而非撥入) 方式來加入會議的參與者，不會聽到個人宣告。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

