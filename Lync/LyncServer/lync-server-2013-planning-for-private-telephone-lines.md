---
title: Lync Server 2013：規劃私人電話線路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0df93d8a8de73a3119e7ca9a1a7abd76e9157a17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="6aebb-102">使用 Lync Server 2013 規劃私人電話線路</span><span class="sxs-lookup"><span data-stu-id="6aebb-102">Planning for private telephone lines with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6aebb-103">_**主題上次修改日期：** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="6aebb-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="6aebb-104">Lync Server 2013 也提供除了主要電話線之外，也可為使用者提供第二部、私人電話線的功能。</span><span class="sxs-lookup"><span data-stu-id="6aebb-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="6aebb-105">您通常會將私人電話線指派給主管人員，以及想要其直接達到未列出電話號碼的其他人。</span><span class="sxs-lookup"><span data-stu-id="6aebb-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="6aebb-106">私人電話線只能使用 Lync Server 管理命令介面來設定。</span><span class="sxs-lookup"><span data-stu-id="6aebb-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="6aebb-107">您無法使用 Lync Server [控制台] 設定私人電話線路。</span><span class="sxs-lookup"><span data-stu-id="6aebb-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="6aebb-108">私人電話線只能在 Lync Server 部署而不是混合式部署中進行設定。</span><span class="sxs-lookup"><span data-stu-id="6aebb-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="6aebb-109">私人電話線路的特性</span><span class="sxs-lookup"><span data-stu-id="6aebb-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="6aebb-110">雖然第二個是私人電話線的概念基本簡單，但請務必瞭解私人線路的特性，以及它們與使用者的主要電話線相似且不同的方式。</span><span class="sxs-lookup"><span data-stu-id="6aebb-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="6aebb-111">私人電話線路的一般特性</span><span class="sxs-lookup"><span data-stu-id="6aebb-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="6aebb-112">一位使用者只能有一個私人電話線路。</span><span class="sxs-lookup"><span data-stu-id="6aebb-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="6aebb-113">擁有私人電話線路的使用者只有一個語音信箱，而且會在單一電子郵件地址收到未接來電通知。</span><span class="sxs-lookup"><span data-stu-id="6aebb-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="6aebb-114">擁有私人電話線的使用者沒有第二個 SIP 位址，第二個私人電話線不會給予使用者第二個在網路上的狀態（例如第二個立即訊息身分識別）。</span><span class="sxs-lookup"><span data-stu-id="6aebb-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="6aebb-115">私人電話線只適用于內部部署部署。</span><span class="sxs-lookup"><span data-stu-id="6aebb-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="6aebb-116">它們無法用於 Lync Server 的託管部署。</span><span class="sxs-lookup"><span data-stu-id="6aebb-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="6aebb-117">私人電話線與主要電話線路有何不同</span><span class="sxs-lookup"><span data-stu-id="6aebb-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="6aebb-118">私人電話線路的電話號碼不會出現在從 Active Directory 網域服務衍生的電話目錄或連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="6aebb-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="6aebb-119">私人電話線不提供下列任何功能：來電轉接、團隊通話、委派、小組振鈴、群組通話，以及回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="6aebb-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="6aebb-120">呼叫私人電話線有特殊的響鈴，通話的系統通知會告訴使用者來電是在他或她的私人線路上。</span><span class="sxs-lookup"><span data-stu-id="6aebb-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="6aebb-121">呼叫專用電話線路的電話總是會響鈴。</span><span class="sxs-lookup"><span data-stu-id="6aebb-121">Calls to the private telephone line always ring through.</span></span> <span data-ttu-id="6aebb-122">它們不會追蹤「請勿打擾」規則。</span><span class="sxs-lookup"><span data-stu-id="6aebb-122">They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="6aebb-123">私人電話線路僅供進貨，不能用來撥出電話。</span><span class="sxs-lookup"><span data-stu-id="6aebb-123">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="6aebb-124">當使用者使用私人電話線路撥打電話時，通話是從使用者的主要電話線發出，而且不會隱藏使用者的名稱或使用者的主要電話號碼（來自呼叫者）。</span><span class="sxs-lookup"><span data-stu-id="6aebb-124">When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="6aebb-125">私人電話線與主要電話線路類似的方式</span><span class="sxs-lookup"><span data-stu-id="6aebb-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="6aebb-126">對於主要電話線（如果已啟用語音信箱），會將未接聽的電話撥打電話至相同的語音信箱收件匣。</span><span class="sxs-lookup"><span data-stu-id="6aebb-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="6aebb-127">通話駐留和通話裝貨使用私人電話線的方式與使用者的主要電話線完全相同。</span><span class="sxs-lookup"><span data-stu-id="6aebb-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="6aebb-128">在使用者的主要電話線上啟用同時撥打時，也會在專線電話線路上啟用。</span><span class="sxs-lookup"><span data-stu-id="6aebb-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="6aebb-129">私人電話線的電話號碼會以與使用者主要電話線的電話號碼相同的方式記錄在通話明細記錄中，但會指出它是私人電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6aebb-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="6aebb-130">使用者在私人電話線上接聽來電之後，該通話就會與使用者的主要電話線上的通話相同。</span><span class="sxs-lookup"><span data-stu-id="6aebb-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="6aebb-131">例如，如果在私人電話線路上接聽通話的使用者轉寄來電或邀請其他人加入電話會議，則使用者的名稱會出現在 Lync 2013 中，而使用者的主要電話線的電話號碼會顯示在本機號碼中。</span><span class="sxs-lookup"><span data-stu-id="6aebb-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="6aebb-132">使用者可以使用與主要電話線相同的方式，在私人電話線上轉移通話（例如行動電話或家用電話，然後再以其他目的地（例如行動電話或家用電話）。</span><span class="sxs-lookup"><span data-stu-id="6aebb-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6aebb-133">當您將私人線路的呼叫路由到備用電話號碼時，備用電話線路的電話號碼會提供給備用電話號碼，而且可顯示在該號碼的記錄中。</span><span class="sxs-lookup"><span data-stu-id="6aebb-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6aebb-134">在傳入系統通知中，從會議到私人電話線路的通話不會有<EM>私線</EM>指示。</span><span class="sxs-lookup"><span data-stu-id="6aebb-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="6aebb-135">管理私人電話線路</span><span class="sxs-lookup"><span data-stu-id="6aebb-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="6aebb-136">除了建立及管理私人電話線的技術方面，您必須為其建立管理程式。</span><span class="sxs-lookup"><span data-stu-id="6aebb-136">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them.</span></span> <span data-ttu-id="6aebb-137">這包括決定組織中誰符合私人線路、建立和維護人員及其電話線路的原則，可能會為主管建立私人的電話目錄、安排使用者訓練，以及相關工作。</span><span class="sxs-lookup"><span data-stu-id="6aebb-137">This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6aebb-138">私人電話線會儲存在 Active Directory 中，做為 user 物件上的 msRTCSIP-PrivateLine 屬性。</span><span class="sxs-lookup"><span data-stu-id="6aebb-138">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object.</span></span> <span data-ttu-id="6aebb-139">根據預設，[經過驗證的使用者] 群組的任何成員都有讀取這個屬性的許可權。</span><span class="sxs-lookup"><span data-stu-id="6aebb-139">By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="6aebb-140">指派電話號碼</span><span class="sxs-lookup"><span data-stu-id="6aebb-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="6aebb-141">使用 Lync Server [控制台] 或 [Lync Server 管理命令介面]，以與不含私人電話線的帳戶相同的方式建立需要私人電話線之新使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6aebb-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="6aebb-142">在 Lync Server 管理命令介面中使用**move-csuser** Cmdlet，將電話號碼指派給使用者的私人電話線路，例如，**設定 move-csuser 身分 "Sip:joe@contoso.com"-PrivateLine "電話： + 14255551212"**。</span><span class="sxs-lookup"><span data-stu-id="6aebb-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="6aebb-143">私人電話線的電話號碼長度可以介於3到15個數字之間，且必須在前面加上「電話：」首碼。</span><span class="sxs-lookup"><span data-stu-id="6aebb-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="6aebb-144">只要您的組織有直接撥打該區號及國家/地區代碼，他們就可以有任何地區代碼及任何國家/地區的程式碼。</span><span class="sxs-lookup"><span data-stu-id="6aebb-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="6aebb-145">如需有關 Cmdlet 和 Lync Server 管理命令介面的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。</span><span class="sxs-lookup"><span data-stu-id="6aebb-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="6aebb-146">混合式部署中的私人電話線路</span><span class="sxs-lookup"><span data-stu-id="6aebb-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="6aebb-147">私人電話線只應針對 Lync Server 的部署進行設定。</span><span class="sxs-lookup"><span data-stu-id="6aebb-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="6aebb-148">在其中同時有 Lync Server 和 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 伺服器的部署中，當較舊版本的使用者嘗試呼叫私人電話線時，呼叫路由失敗的原因是伺服器無法在私人電話線路上執行反向編號查閱。</span><span class="sxs-lookup"><span data-stu-id="6aebb-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

