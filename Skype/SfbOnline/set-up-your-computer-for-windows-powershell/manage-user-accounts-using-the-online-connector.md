---
title: 使用線上連接器管理使用者帳戶
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 在 Windows powerShell Get-CsOnlineUser Cmdlet 中使用 Cmdlet 來取得貴組織的商務用 Skype Online 使用者相關資訊。
ms.openlocfilehash: bdf1d445fa7c0a9ac4f874e0983b8ab7e8cb19e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113169"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="3a41b-103">使用線上連接器管理使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="3a41b-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="3a41b-104">管理使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="3a41b-104">Manage user accounts</span></span>

<span data-ttu-id="3a41b-105">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="3a41b-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="3a41b-106">傳回所有 Lync Online 使用者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="3a41b-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="3a41b-107">在商務用 Skype Online 中返回特定使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="3a41b-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="3a41b-108">在商務用 Skype Online 中，針對特定使用者返回特定資訊</span><span class="sxs-lookup"><span data-stu-id="3a41b-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="3a41b-109">在商務用 Skype Online 中返回已篩選的使用者清單</span><span class="sxs-lookup"><span data-stu-id="3a41b-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="3a41b-110">**Set-CsUser** Cmdlet 也包含在商務用 Skype Online 系統管理員可用的一組 Cmdlet 中。</span><span class="sxs-lookup"><span data-stu-id="3a41b-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="3a41b-111">不過，除了設定 _AudioVideoDisabled_ 參數之外 **，Set-CsUser** 目前無法用來管理商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="3a41b-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="3a41b-112">如果您嘗試使用任何其他參數執行 Cmdlet，它會失敗，出現錯誤訊息類似：無法設定「SipAddress」。</span><span class="sxs-lookup"><span data-stu-id="3a41b-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="3a41b-113">此參數在遠端租使用者 PowerShell 中受到限制。</span><span class="sxs-lookup"><span data-stu-id="3a41b-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="3a41b-114">傳回所有 Lync Online 使用者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="3a41b-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="3a41b-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="3a41b-115"><a name="BKAllUsers"> </a></span></span>

<span data-ttu-id="3a41b-116">若要返回已啟用商務用 Skype Online 的所有使用者相關資訊，請撥打 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) Cmdlet，而不需要任何其他參數。</span><span class="sxs-lookup"><span data-stu-id="3a41b-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="3a41b-117">若要返回單一隨機選取使用者 (的資訊，例如，若要使用此帳戶做為測試用途) ，請撥打 **Get-CsOnlineUser** Cmdlet，將 _ResultSize_ 參數設為 1。</span><span class="sxs-lookup"><span data-stu-id="3a41b-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="3a41b-118">這會使 **Get-CsOnlineUser** Cmdlet 只針對一個使用者返回資訊，無論您組織中有多少使用者。</span><span class="sxs-lookup"><span data-stu-id="3a41b-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="3a41b-119">若要返回五個使用者的資訊，請設定 _ResultSize 參數_ 的值為 5。</span><span class="sxs-lookup"><span data-stu-id="3a41b-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="3a41b-120">在商務用 Skype Online 中返回特定使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="3a41b-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="3a41b-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="3a41b-121"><a name="BKSpecificUser"> </a></span></span>

<span data-ttu-id="3a41b-122">在呼叫 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) Cmdlet 時，有多種方式可參照特定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3a41b-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="3a41b-123">您可以使用使用者的 Active Directory 網域服務 (AD DS) 顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="3a41b-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="3a41b-124">您可以使用使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="3a41b-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="3a41b-125">您可以使用使用者的使用者主體名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="3a41b-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="3a41b-126">在商務用 Skype Online 中，針對特定使用者返回特定資訊</span><span class="sxs-lookup"><span data-stu-id="3a41b-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="3a41b-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="3a41b-127"><a name="BKSpecificUsers"> </a></span></span>

<span data-ttu-id="3a41b-128">根據預設 [，Get-CsOnlineUser Cmdlet](/powershell/module/skype/Get-CsOnlineUser) 會針對每個商務用 Skype Online 使用者帳戶，返回大量的資訊。</span><span class="sxs-lookup"><span data-stu-id="3a41b-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="3a41b-129">如果您只對該資訊的子集感興趣，請用管道將返回的資料傳輸至 **Select-Object** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a41b-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="3a41b-130">例如，此命令會為使用者 Ken Myer 返回所有資料，然後使用 **Select-Object** Cmdlet 將螢幕上顯示的資訊限制為 Ken 的 AD DS 顯示名稱和撥號方案。</span><span class="sxs-lookup"><span data-stu-id="3a41b-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="3a41b-131">下列命令會針對所有使用者返回顯示名稱和撥號方案。</span><span class="sxs-lookup"><span data-stu-id="3a41b-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="3a41b-132">若要尋找商務用 Skype Online 使用者帳戶的屬性，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="3a41b-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="3a41b-133">在商務用 Skype Online 中返回已篩選的使用者清單</span><span class="sxs-lookup"><span data-stu-id="3a41b-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="3a41b-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="3a41b-134"><a name="BKListofUsers"> </a></span></span>

<span data-ttu-id="3a41b-135">使用 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) Cmdlet 和 _LdapFilter_ 或 _Filter_ 參數，您可以輕鬆地返回一組目標使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="3a41b-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="3a41b-136">例如，此命令會返回在財務部門工作的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="3a41b-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="3a41b-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="3a41b-137">Related topics</span></span>
[<span data-ttu-id="3a41b-138">使用 Windows PowerShell 設定商務用 Skype 線上管理的電腦</span><span class="sxs-lookup"><span data-stu-id="3a41b-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)