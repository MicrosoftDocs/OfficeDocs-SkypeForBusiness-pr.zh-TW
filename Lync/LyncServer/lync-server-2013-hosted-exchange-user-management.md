---
title: Lync Server 2013：主控 Exchange 使用者管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="b66ee-102">Lync Server 2013 中的主控 Exchange 使用者管理</span><span class="sxs-lookup"><span data-stu-id="b66ee-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b66ee-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b66ee-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b66ee-104">若要為 Lync Server 2013 使用者提供語音信箱服務，而其信箱是位於託管 Exchange 服務的使用者，您必須啟用其使用者帳戶來存放託管的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b66ee-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b66ee-105">在 Lync Server 2013 使用者可以啟用託管語音信箱之前，必須先部署適用于對應使用者帳戶的託管語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="b66ee-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="b66ee-106">只要將原則套用到您想要啟用的使用者，原則就可以是全域、網站或每位使用者。</span><span class="sxs-lookup"><span data-stu-id="b66ee-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="b66ee-107">如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="b66ee-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="b66ee-108">MsExchUCVoiceMailSettings 屬性</span><span class="sxs-lookup"><span data-stu-id="b66ee-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="b66ee-109">Lync Server 2013 引入一個名為**msExchUCVoiceMailSettings**的新使用者屬性，該使用者是作為 Lync Server 2013 Active Directory 架構準備的一部分建立的。</span><span class="sxs-lookup"><span data-stu-id="b66ee-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="b66ee-110">這個多重值屬性可保留 Lync Server 2013 和託管 Exchange 服務所共用的語音信箱設定。</span><span class="sxs-lookup"><span data-stu-id="b66ee-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="b66ee-111">在某些情況下，託管 Exchange 服務可能會在啟用 Exchange UM 的程式中設定 msExchUCVoiceMailSettings 屬性的值，或在將信箱轉移至託管 Exchange 伺服器的程式期間設定。</span><span class="sxs-lookup"><span data-stu-id="b66ee-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="b66ee-112">如果 Exchange 未設定此屬性，則 Lync Server 2013 系統管理員必須執行 Move-csuser Cmdlet 來設定它，如本主題前面所述。</span><span class="sxs-lookup"><span data-stu-id="b66ee-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="b66ee-113">屬性的鍵/值對及其作者如下表所示。</span><span class="sxs-lookup"><span data-stu-id="b66ee-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="b66ee-114">MsExchUCVoiceMailSettings 屬性鍵/值對</span><span class="sxs-lookup"><span data-stu-id="b66ee-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b66ee-115">值</span><span class="sxs-lookup"><span data-stu-id="b66ee-115">Value</span></span></th>
<th><span data-ttu-id="b66ee-116">撰寫</span><span class="sxs-lookup"><span data-stu-id="b66ee-116">Author</span></span></th>
<th><span data-ttu-id="b66ee-117">意味</span><span class="sxs-lookup"><span data-stu-id="b66ee-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b66ee-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="b66ee-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="b66ee-119">證券</span><span class="sxs-lookup"><span data-stu-id="b66ee-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="b66ee-120">使用者已啟用 Exchange Server 的託管 UM 存取權。</span><span class="sxs-lookup"><span data-stu-id="b66ee-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="b66ee-121">Exchange UM 路由應用程式將會檢查使用者的託管語音信箱原則，以取得路由詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b66ee-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b66ee-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="b66ee-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="b66ee-123">證券</span><span class="sxs-lookup"><span data-stu-id="b66ee-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="b66ee-124">已停用 Exchange Server 的託管 UM 存取的使用者。</span><span class="sxs-lookup"><span data-stu-id="b66ee-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b66ee-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="b66ee-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="b66ee-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="b66ee-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="b66ee-127">使用者已啟用 Lync Server 2013 的託管 UM 存取權。</span><span class="sxs-lookup"><span data-stu-id="b66ee-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="b66ee-128">Lync Server 2013 ExUM 路由應用程式將會檢查使用者的託管語音信箱原則，以取得路由詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b66ee-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b66ee-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="b66ee-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="b66ee-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="b66ee-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="b66ee-131">已停用 Lync Server 2013 的託管 UM 存取的使用者。</span><span class="sxs-lookup"><span data-stu-id="b66ee-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b66ee-132">如果屬性已有一個 Lync Server 2013 鍵/值對以外的值（CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1），則會出現警告，指出該屬性可能是由不同的應用程式來管理。</span><span class="sxs-lookup"><span data-stu-id="b66ee-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="b66ee-133">例如，如果鍵/值對 ExchangeHostedVoiceMail = 0 或 ExchangeHostedVoiceMail = 1 已存在，則會顯示警告。</span><span class="sxs-lookup"><span data-stu-id="b66ee-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="b66ee-134">在這種情況下，您可以透過編輯 Active Directory 來變更值，或執行下列 Cmdlet，將此值設定為 null：</span><span class="sxs-lookup"><span data-stu-id="b66ee-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="b66ee-135">Move-csuser –身分識別使用者– HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="b66ee-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="b66ee-136">允許使用者擁有託管的語音信箱</span><span class="sxs-lookup"><span data-stu-id="b66ee-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="b66ee-137">若要讓使用者的語音信箱呼叫路由至託管 Exchange UM，您必須執行 Move-csuser Cmdlet 來設定*HostedVoiceMail*參數的值。</span><span class="sxs-lookup"><span data-stu-id="b66ee-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="b66ee-138">這個參數也會通知 Lync Server 2013，以淺您的「撥號語音信箱」指標。</span><span class="sxs-lookup"><span data-stu-id="b66ee-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="b66ee-139">下列範例會針對託管語音信箱啟用 Pilar 方的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="b66ee-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="b66ee-140">此 Cmdlet 會驗證託管的語音信箱原則（全域、網站層級或每位使用者）適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="b66ee-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="b66ee-141">如果沒有套用任何原則，則 Cmdlet 失敗。</span><span class="sxs-lookup"><span data-stu-id="b66ee-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="b66ee-142">下列範例會針對託管語音信箱停用 Pilar 方的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="b66ee-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="b66ee-143">此 Cmdlet 會確認沒有任何託管的語音信箱原則（全域、網站層級或每位使用者）適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="b66ee-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="b66ee-144">如果已套用原則，則 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="b66ee-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="b66ee-145">如需有關使用 Move-csuser Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="b66ee-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

