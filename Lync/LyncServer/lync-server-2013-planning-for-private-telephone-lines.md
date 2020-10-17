---
title: Lync Server 2013：規劃私人電話線
description: Lync Server 2013：規劃私人電話線。
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
ms.openlocfilehash: 120c1804bc3ce58e8746f68cbda9c66f02568ccb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549309"
---
# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="8e1b8-103">使用 Lync Server 2013 規劃私人電話線</span><span class="sxs-lookup"><span data-stu-id="8e1b8-103">Planning for private telephone lines with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e1b8-104">_**主題上次修改日期：** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="8e1b8-104">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="8e1b8-105">Lync Server 2013 引進除了主要電話線之外，也可為使用者提供第二部私人電話線。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-105">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="8e1b8-106">私人電話線通常會指派給主管人員和其他人，其可直接到達未列出的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="8e1b8-107">私人電話線只能使用 Lync Server 管理命令介面來設定。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-107">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="8e1b8-108">您無法使用 Lync Server [控制台] 設定私人電話線。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-108">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="8e1b8-109">私人電話線應該只在部署 Lync Server 時設定，而不是在混合部署中設定。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-109">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="8e1b8-110">私人電話線的特性</span><span class="sxs-lookup"><span data-stu-id="8e1b8-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="8e1b8-111">雖然第二個私人電話線的概念基本上很簡單，但是請務必瞭解私人線路的特性，以及它們與使用者的主要電話線的類似之處和不同之處的方式。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="8e1b8-112">私人電話線的一般特性</span><span class="sxs-lookup"><span data-stu-id="8e1b8-112">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="8e1b8-113">使用者只能有一個私人電話線。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-113">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="8e1b8-114">具有私人電話線的使用者只有一個語音信箱，並在單一電子郵件地址接收未接來電通知。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="8e1b8-115">具有私人電話線的使用者沒有第二個 SIP 位址，第二部私人電話線不會讓使用者在網路上有第二個存在的狀態 (例如，第二個立即訊息身分識別) 。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="8e1b8-116">私人電話線只適用于內部部署部署。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="8e1b8-117">它們不適用於 Lync Server 的託管部署。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-117">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="8e1b8-118">私人電話線與主要電話線的區別</span><span class="sxs-lookup"><span data-stu-id="8e1b8-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="8e1b8-119">私人電話線的電話號碼不會出現在從 Active Directory 網域服務衍生的電話目錄或連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="8e1b8-120">私人電話線沒有下列任何功能：「來電轉接」、「小組通話」、「委派」、「小組振鈴」、「群組通話挑選」和「回應群組」應用程式。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="8e1b8-121">撥打私人電話線的電話有特殊的震鈴，而且呼叫的系統通知會告訴使用者，來電是在其私人線路上。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="8e1b8-122">對私人電話線的來電一定會來電。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-122">Calls to the private telephone line always ring through.</span></span> <span data-ttu-id="8e1b8-123">它們不遵循「請勿打擾」規則。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-123">They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="8e1b8-124">私人電話線只是輸入，無法用來撥打撥出電話。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="8e1b8-125">當具有私人電話線的使用者撥打通話時，此呼叫來自使用者的主要電話線，而且不會隱藏使用者的名稱或使用者的主要電話號碼（來自呼叫者）。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-125">When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="8e1b8-126">私人電話線與主要電話線的相似之處</span><span class="sxs-lookup"><span data-stu-id="8e1b8-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="8e1b8-127">對私人電話線的未接聽呼叫會路由傳送至與主要電話線 (，如果已啟用語音信箱) 中的 [語音信箱] 收件匣。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="8e1b8-128">通話駐留及呼叫收取的運作方式與私人電話線完全相同，與使用者的主要電話線相同。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="8e1b8-129">在使用者的主要電話線上啟用同時震鈴時，也會在私人電話線上啟用同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-129">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="8e1b8-130">私人電話線的電話號碼會記錄在通話詳細資料記錄中，其方式與使用者主要電話線的電話號碼相同，但是會指出其為私人電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="8e1b8-131">在使用者接聽私人電話線上的來電之後，通話會與使用者的主要電話線上的呼叫進行相同的處理。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="8e1b8-132">例如，如果接收私人電話線上之來電的使用者轉寄來電或邀請其他人加入電話會議，使用者的名稱會出現在 Lync 2013 中，而且使用者主要電話線的電話號碼會顯示在來電者識別碼中。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="8e1b8-133">使用者可以轉移來電 (將來電重新導向至另一個目的地（如行動電話或住家電話），再以與主要電話線相同的方式，從私人電話線進行回應) 。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e1b8-134">當私人線路呼叫路由傳送至其他電話號碼時，可將私人電話線的電話號碼提供給其他電話號碼，並顯示在該號碼的記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e1b8-135">從會議到私人電話線的呼叫，在傳入系統通知中不會有 <EM>私密金鑰</EM> 指示。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-135">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="8e1b8-136">管理私人電話線</span><span class="sxs-lookup"><span data-stu-id="8e1b8-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="8e1b8-137">除了建立及管理私人電話線的技術層面之外，您還需要為他們建立系統管理程式。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-137">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them.</span></span> <span data-ttu-id="8e1b8-138">這包括決定組織中誰符合私人行的原則、建立及維護人員及其電話線的清單，可能會為主管人員建立私人的電話目錄，以及為使用者訓練進行安排，以及相關的任務。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-138">This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e1b8-139">私人電話線會儲存在 Active Directory 中，做為使用者物件上的 msRTCSIP-PrivateLine 屬性。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-139">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object.</span></span> <span data-ttu-id="8e1b8-140">根據預設，已驗證使用者群組的任何成員都具有此屬性的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-140">By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="8e1b8-141">指派電話號碼</span><span class="sxs-lookup"><span data-stu-id="8e1b8-141">Assigning Telephone Numbers</span></span>

<span data-ttu-id="8e1b8-142">使用 Lync Server 控制台或 Lync Server 管理命令介面，以與不含私人電話線的帳戶相同的方式，建立需要私人電話線之新使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="8e1b8-143">使用 Lync Server 管理命令介面中的 **Set-CsUser** Cmdlet，將電話號碼指派給使用者的私人電話線，例如 **Set-CsUser 身分 "sip:joe@contoso.com"-PrivateLine "電話： + 14255551212"**。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-143">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="8e1b8-144">私人電話線的電話號碼長度可以介於3到15個數字之間，且前面必須加上 "TEL:" 前置詞。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="8e1b8-145">只要您的組織對該區號和國家/地區碼進行直接撥號，他們就可以擁有任何區功能變數代碼和任何國家/地區碼。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="8e1b8-146">如需 Cmdlet 和 Lync Server 管理命令介面的詳細資訊，請參閱 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面檔。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-146">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="8e1b8-147">混合式部署中的私人電話線</span><span class="sxs-lookup"><span data-stu-id="8e1b8-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="8e1b8-148">私人電話線應該只針對 Lync Server 的部署進行設定。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-148">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="8e1b8-149">在具有 Lync Server 和 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 伺服器的部署中，當舊版使用者嘗試撥打私人電話線時，路由呼叫會失敗，因為伺服器無法在私人電話線上執行反向號碼查閱。</span><span class="sxs-lookup"><span data-stu-id="8e1b8-149">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

