---
title: Lync Server 2013：主控 Exchange 使用者管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504200"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="891af-102">Lync Server 2013 中的主控 Exchange 使用者管理</span><span class="sxs-lookup"><span data-stu-id="891af-102">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="891af-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="891af-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="891af-104">若要為 Lync Server 2013 使用者提供語音信箱服務，其信箱位於主控 Exchange 服務上，您必須為主控的語音信箱啟用使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="891af-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="891af-105">在 Lync Server 2013 使用者可以啟用裝載的語音信箱之前，必須先部署適用于對應使用者帳戶的主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="891af-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="891af-106">原則可以是全域、網站或每位使用者在範圍內，只要它套用至您想要啟用的使用者。</span><span class="sxs-lookup"><span data-stu-id="891af-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="891af-107">如需詳細資訊，請參閱 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="891af-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="891af-108">msExchUCVoiceMailSettings 屬性</span><span class="sxs-lookup"><span data-stu-id="891af-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="891af-109">Lync Server 2013 引進新的使用者屬性，名為 **msExchUCVoiceMailSettings**，它是 Lync Server 2013 Active Directory 架構準備的一部分所建立。</span><span class="sxs-lookup"><span data-stu-id="891af-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="891af-110">此多重值屬性可容納 Lync Server 2013 和主控 Exchange 服務共用的語音信箱設定。</span><span class="sxs-lookup"><span data-stu-id="891af-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="891af-111">在某些情況下，裝載 Exchange 服務可能會在啟用 Exchange UM 的程式中設定 msExchUCVoiceMailSettings 屬性的值，或將信箱轉移至主控 Exchange 伺服器的過程中。</span><span class="sxs-lookup"><span data-stu-id="891af-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="891af-112">如果 Exchange 未設定此屬性，Lync Server 2013 系統管理員必須執行 Set-CsUser Cmdlet 來設定此屬性，如本主題稍早所述。</span><span class="sxs-lookup"><span data-stu-id="891af-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="891af-113">下表顯示內容的索引鍵/值對及其作者。</span><span class="sxs-lookup"><span data-stu-id="891af-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="891af-114">MsExchUCVoiceMailSettings 屬性索引鍵/值組</span><span class="sxs-lookup"><span data-stu-id="891af-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="891af-115">值</span><span class="sxs-lookup"><span data-stu-id="891af-115">Value</span></span></th>
<th><span data-ttu-id="891af-116">作者</span><span class="sxs-lookup"><span data-stu-id="891af-116">Author</span></span></th>
<th><span data-ttu-id="891af-117">意義</span><span class="sxs-lookup"><span data-stu-id="891af-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="891af-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="891af-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="891af-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="891af-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="891af-120">Exchange Server 已啟用使用者的裝載 UM 存取。</span><span class="sxs-lookup"><span data-stu-id="891af-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="891af-121">Exchange UM 路由應用程式會檢查使用者的主控語音信箱原則，以取得路由詳細資料。</span><span class="sxs-lookup"><span data-stu-id="891af-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891af-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="891af-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="891af-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="891af-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="891af-124">Exchange Server 已停用使用者的裝載 UM 存取。</span><span class="sxs-lookup"><span data-stu-id="891af-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891af-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="891af-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="891af-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="891af-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="891af-127">使用者已啟用 Lync Server 2013 的託管 UM 存取。</span><span class="sxs-lookup"><span data-stu-id="891af-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="891af-128">Lync Server 2013 ExUM 路由應用程式會檢查使用者的主控語音信箱原則，以取得路由詳細資料。</span><span class="sxs-lookup"><span data-stu-id="891af-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891af-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="891af-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="891af-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="891af-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="891af-131">Lync Server 2013 已停用使用者的裝載 UM 存取。</span><span class="sxs-lookup"><span data-stu-id="891af-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="891af-132">如果此屬性已有一個不同的 Lync Server 2013 機碼/值組值 (CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1) ，則警告會指出該屬性可能是由其他應用程式所管理。</span><span class="sxs-lookup"><span data-stu-id="891af-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="891af-133">例如，如果索引鍵/值組 ExchangeHostedVoiceMail = 0 或 ExchangeHostedVoiceMail = 1 已存在，就會顯示警告。</span><span class="sxs-lookup"><span data-stu-id="891af-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="891af-134">在此情況下，您可以透過編輯 Active Directory 來變更值，或執行下列 Cmdlet，將值設定為 null：</span><span class="sxs-lookup"><span data-stu-id="891af-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="891af-135">Set-CsUser –身分識別使用者– HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="891af-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="891af-136">為使用者啟用主控語音信箱</span><span class="sxs-lookup"><span data-stu-id="891af-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="891af-137">若要讓使用者的語音信箱呼叫路由傳送至主控 Exchange UM，您必須執行 Set-CsUser Cmdlet 來設定 *HostedVoiceMail* 參數的值。</span><span class="sxs-lookup"><span data-stu-id="891af-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="891af-138">這個參數也會向 Lync Server 2013 發出「呼叫語音信箱」指示器。</span><span class="sxs-lookup"><span data-stu-id="891af-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="891af-139">下列範例會為主控語音信箱啟用 Pilar Ackerman 的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="891af-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="891af-140">此 Cmdlet 會驗證主控的語音信箱原則 (全域、網站層級或每位使用者) 適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="891af-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="891af-141">若未套用原則，指令 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="891af-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="891af-142">下列範例會停用 Pilar Ackerman 的使用者帳戶進行主控語音信箱：</span><span class="sxs-lookup"><span data-stu-id="891af-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="891af-143">此 Cmdlet 會驗證沒有任何主控的語音信箱原則 (全域、網站層級或每位使用者) 適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="891af-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="891af-144">若原則已套用，指令 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="891af-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="891af-145">如需使用 Set-CsUser Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="891af-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

