---
title: 使用商務用 Skype 規劃私人電話線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 在商務用 Skype Server Enterprise Voice 中規劃私人（次要）電話線。
ms.openlocfilehash: 001a83e4bd81f0f47546f51f1d4993c6b1cec4bf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802563"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="3aa77-103">使用商務用 Skype 規劃私人電話線</span><span class="sxs-lookup"><span data-stu-id="3aa77-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="3aa77-104">在商務用 Skype Server Enterprise Voice 中規劃私人（次要）電話線。</span><span class="sxs-lookup"><span data-stu-id="3aa77-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3aa77-105">[商務用 Skype 伺服器] 可讓您除了主要電話線之外，也可以為使用者提供第二部、私人電話線路。</span><span class="sxs-lookup"><span data-stu-id="3aa77-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="3aa77-106">您通常會將私人電話線指派給主管人員，以及想要其直接達到未列出電話號碼的其他人。</span><span class="sxs-lookup"><span data-stu-id="3aa77-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="3aa77-107">私人電話線只能使用商務用 Skype Server Management Shell 來設定。</span><span class="sxs-lookup"><span data-stu-id="3aa77-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3aa77-108">您無法使用商務用 Skype Server [控制台] 來設定私人電話線路。</span><span class="sxs-lookup"><span data-stu-id="3aa77-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3aa77-109">私人電話線只能在部署商務用 Skype Server 而不是混合式部署中進行設定。</span><span class="sxs-lookup"><span data-stu-id="3aa77-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="3aa77-110">私人電話線路的特性</span><span class="sxs-lookup"><span data-stu-id="3aa77-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="3aa77-111">雖然第二個是私人電話線的概念基本簡單，但請務必瞭解私人線路的特性，以及它們與使用者的主要電話線相似且不同的方式。</span><span class="sxs-lookup"><span data-stu-id="3aa77-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="3aa77-112">私人電話線路的一般特性</span><span class="sxs-lookup"><span data-stu-id="3aa77-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="3aa77-113">一位使用者只能有一個私人電話線路。</span><span class="sxs-lookup"><span data-stu-id="3aa77-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="3aa77-114">擁有私人電話線路的使用者只有一個語音信箱，而且會在單一電子郵件地址收到未接來電通知。</span><span class="sxs-lookup"><span data-stu-id="3aa77-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="3aa77-115">擁有私人電話線的使用者沒有第二個 SIP 位址，第二個私人電話線不會給予使用者第二個在網路上的狀態（例如第二個立即訊息身分識別）。</span><span class="sxs-lookup"><span data-stu-id="3aa77-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="3aa77-116">私人電話線只適用于內部部署部署。</span><span class="sxs-lookup"><span data-stu-id="3aa77-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="3aa77-117">它們無法用於商務用 Skype Server 的託管部署。</span><span class="sxs-lookup"><span data-stu-id="3aa77-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="3aa77-118">私人電話線與主要電話線路有何不同</span><span class="sxs-lookup"><span data-stu-id="3aa77-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="3aa77-119">私人電話線路的電話號碼不會出現在從 Active Directory 網域服務衍生的電話目錄或連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="3aa77-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="3aa77-120">私人電話線不提供下列任何功能：來電轉接、團隊通話、委派、小組振鈴、群組通話，以及回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="3aa77-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="3aa77-121">呼叫私人電話線有特殊的響鈴，通話的系統通知會告訴使用者來電是在他或她的私人線路上。</span><span class="sxs-lookup"><span data-stu-id="3aa77-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="3aa77-122">呼叫專用電話線路的電話總是會響鈴。</span><span class="sxs-lookup"><span data-stu-id="3aa77-122">Calls to the private telephone line always ring through.</span></span> <span data-ttu-id="3aa77-123">它們不會追蹤「請勿打擾」規則。</span><span class="sxs-lookup"><span data-stu-id="3aa77-123">They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="3aa77-124">私人電話線路僅供進貨，不能用來撥出電話。</span><span class="sxs-lookup"><span data-stu-id="3aa77-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="3aa77-125">當使用者使用私人電話線路撥打電話時，通話是從使用者的主要電話線發出，而且不會隱藏使用者的名稱或使用者的主要電話號碼（來自呼叫者）。</span><span class="sxs-lookup"><span data-stu-id="3aa77-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="3aa77-126">私人電話線與主要電話線路類似的方式</span><span class="sxs-lookup"><span data-stu-id="3aa77-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="3aa77-127">對於主要電話線（如果已啟用語音信箱），會將未接聽的電話撥打電話至相同的語音信箱收件匣。</span><span class="sxs-lookup"><span data-stu-id="3aa77-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="3aa77-128">通話駐留和通話裝貨使用私人電話線的方式與使用者的主要電話線完全相同。</span><span class="sxs-lookup"><span data-stu-id="3aa77-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="3aa77-129">在使用者的主要電話線上啟用同時撥打時，也會在專線電話線路上啟用。</span><span class="sxs-lookup"><span data-stu-id="3aa77-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="3aa77-130">私人電話線的電話號碼會以與使用者主要電話線的電話號碼相同的方式記錄在通話明細記錄中，但會指出它是私人電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3aa77-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="3aa77-131">使用者在私人電話線上接聽來電之後，該通話就會與使用者的主要電話線上的通話相同。</span><span class="sxs-lookup"><span data-stu-id="3aa77-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="3aa77-132">例如，如果在私人電話線路上接聽通話的使用者轉寄來電或邀請其他人加入電話會議，使用者的名稱會出現在商務用 Skype 中，而使用者的主要電話線的電話號碼則會出現在本機號碼中。</span><span class="sxs-lookup"><span data-stu-id="3aa77-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="3aa77-133">使用者可以使用與主要電話線相同的方式，在私人電話線上轉移通話（例如行動電話或家用電話，然後再以其他目的地（例如行動電話或家用電話）。</span><span class="sxs-lookup"><span data-stu-id="3aa77-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3aa77-134">當您將私人線路的呼叫路由到備用電話號碼時，備用電話線路的電話號碼會提供給備用電話號碼，而且可顯示在該號碼的記錄中。</span><span class="sxs-lookup"><span data-stu-id="3aa77-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="3aa77-135">在傳入系統通知中，從會議到私人電話線路的通話不會有*私線*指示。</span><span class="sxs-lookup"><span data-stu-id="3aa77-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="3aa77-136">管理私人電話線路</span><span class="sxs-lookup"><span data-stu-id="3aa77-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="3aa77-137">除了建立及管理私人電話線的技術方面，您必須為其建立管理程式。</span><span class="sxs-lookup"><span data-stu-id="3aa77-137">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them.</span></span> <span data-ttu-id="3aa77-138">這包括決定組織中誰符合私人線路、建立和維護人員及其電話線路的原則，可能會為主管建立私人的電話目錄、安排使用者訓練，以及相關工作。</span><span class="sxs-lookup"><span data-stu-id="3aa77-138">This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3aa77-139">私人電話線會儲存在 Active Directory 中，做為 user 物件上的 msRTCSIP-PrivateLine 屬性。</span><span class="sxs-lookup"><span data-stu-id="3aa77-139">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object.</span></span> <span data-ttu-id="3aa77-140">根據預設，[經過驗證的使用者] 群組的任何成員都有讀取這個屬性的許可權。</span><span class="sxs-lookup"><span data-stu-id="3aa77-140">By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="3aa77-141">指派電話號碼</span><span class="sxs-lookup"><span data-stu-id="3aa77-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="3aa77-142">使用商務用 Skype Server [控制台] 或 [商務用 Skype 伺服器管理] 命令介面，以與其他需要私人電話線路的使用者相同的方式來建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="3aa77-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="3aa77-143">在商務用 Skype Server Management 命令介面中使用**move-csuser** Cmdlet，將電話號碼指派給使用者的私人電話線路，例如，**將 move-csuser 身分識別 "Sip:joe@contoso.com"-PrivateLine "電話： + 14255551212"**。</span><span class="sxs-lookup"><span data-stu-id="3aa77-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="3aa77-144">私人電話線的電話號碼長度可以介於3到15個數字之間，且必須在前面加上「電話：」首碼。</span><span class="sxs-lookup"><span data-stu-id="3aa77-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="3aa77-145">只要您的組織有直接撥打該區號及國家/地區代碼，他們就可以有任何地區代碼及任何國家/地區的程式碼。</span><span class="sxs-lookup"><span data-stu-id="3aa77-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="3aa77-146">如需有關 Cmdlet 與商務用 Skype Server Management 命令介面的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="3aa77-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="3aa77-147">混合式部署中的私人電話線路</span><span class="sxs-lookup"><span data-stu-id="3aa77-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="3aa77-148">只有在部署商務用 Skype Server 或 Lync Server 2013 時，才能設定私人電話線路。</span><span class="sxs-lookup"><span data-stu-id="3aa77-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="3aa77-149">在有執行舊版 Lync Server 的伺服器的部署中，當舊版的使用者嘗試撥打電話給私人電話線時，呼叫路由失敗的原因是伺服器無法在私人電話線路上執行反向號碼查閱。</span><span class="sxs-lookup"><span data-stu-id="3aa77-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

