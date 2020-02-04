---
title: 管理使用者帳戶
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
description: 在 Windows PowerShell 中使用 CsOnlineUser Cmdlet，以取得貴組織商務用 Skype Online 使用者的相關資訊。
ms.openlocfilehash: 97d717d3472ae96dc66ad58ee5699f3f646a0f3b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706238"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="e1dad-103">管理使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e1dad-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="e1dad-104">管理使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e1dad-104">Manage user accounts</span></span>

<span data-ttu-id="e1dad-105">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="e1dad-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e1dad-106">傳回所有 Lync Online 使用者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="e1dad-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="e1dad-107">在商務用 Skype Online 中針對特定使用者返回資訊</span><span class="sxs-lookup"><span data-stu-id="e1dad-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="e1dad-108">針對商務用 Skype Online 中的特定使用者傳回特定資訊</span><span class="sxs-lookup"><span data-stu-id="e1dad-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="e1dad-109">在商務用 Skype Online 中返回篩選的使用者清單</span><span class="sxs-lookup"><span data-stu-id="e1dad-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="e1dad-110">**Move-csuser** Cmdlet 也包含在商務用 Skype Online 系統管理員所提供的一組 Cmdlet 中。</span><span class="sxs-lookup"><span data-stu-id="e1dad-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="e1dad-111">不過， **move-csuser**目前無法用來管理商務用 Skype Online，除非設定_AudioVideoDisabled_參數。</span><span class="sxs-lookup"><span data-stu-id="e1dad-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="e1dad-112">如果您嘗試使用任何其他參數執行 Cmdlet，則會失敗，並出現類似以下的錯誤訊息：無法設定 "SipAddress"。</span><span class="sxs-lookup"><span data-stu-id="e1dad-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="e1dad-113">此參數在遠端租使用者 PowerShell 中受到限制。</span><span class="sxs-lookup"><span data-stu-id="e1dad-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="e1dad-114">傳回所有 Lync Online 使用者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="e1dad-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="e1dad-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dad-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span></span>

<span data-ttu-id="e1dad-116">若要傳回已針對商務用 Skype Online 啟用的所有使用者的相關資訊，請呼叫[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet （不含任何其他參數）。</span><span class="sxs-lookup"><span data-stu-id="e1dad-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="e1dad-117">若要針對單一、隨機選取的使用者傳回信息（例如，將此帳戶用於測試目的），請呼叫**CsOnlineUser** Cmdlet，並將_ResultSize_參數設定為1。</span><span class="sxs-lookup"><span data-stu-id="e1dad-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="e1dad-118">這會讓**CsOnlineUser** Cmdlet 只傳回一位使用者的資訊，不論貴組織有多少使用者。</span><span class="sxs-lookup"><span data-stu-id="e1dad-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="e1dad-119">若要傳回五個使用者的資訊，請將_ResultSize_參數的值設定為5。</span><span class="sxs-lookup"><span data-stu-id="e1dad-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="e1dad-120">在商務用 Skype Online 中針對特定使用者返回資訊</span><span class="sxs-lookup"><span data-stu-id="e1dad-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="e1dad-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dad-121"><a name="BKMKReturnInfoSpecificUser"> </a></span></span>

<span data-ttu-id="e1dad-122">在呼叫[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 時，有多種方式可以參考特定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e1dad-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="e1dad-123">您可以使用使用者的 Active Directory 網域服務（AD DS）顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="e1dad-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="e1dad-124">您可以使用使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="e1dad-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="e1dad-125">您可以使用使用者的使用者主要名稱（UPN）。</span><span class="sxs-lookup"><span data-stu-id="e1dad-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="e1dad-126">針對商務用 Skype Online 中的特定使用者傳回特定資訊</span><span class="sxs-lookup"><span data-stu-id="e1dad-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="e1dad-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dad-127"><a name="BKMKReturninfoSpecificUsers"> </a></span></span>

<span data-ttu-id="e1dad-128">根據預設， [CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) Cmdlet 會針對每個商務用 Skype Online 使用者帳戶傳回大量的資訊。</span><span class="sxs-lookup"><span data-stu-id="e1dad-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="e1dad-129">如果您只對該資訊的子集感興趣，請將傳回的資料管道傳送給**Select 物件**Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e1dad-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="e1dad-130">例如，這個命令會傳回使用者 Ken Myer 的所有資料，然後使用**Select 物件**Cmdlet 來限制在螢幕上顯示的資訊，以便將顯示的資訊限制在與 KEN 的 AD DS 顯示名稱和撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="e1dad-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="e1dad-131">下列命令會傳回所有使用者的顯示名稱和撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="e1dad-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="e1dad-132">若要尋找商務用 Skype Online 使用者帳戶的屬性，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="e1dad-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="e1dad-133">在商務用 Skype Online 中返回篩選的使用者清單</span><span class="sxs-lookup"><span data-stu-id="e1dad-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="e1dad-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e1dad-134"><a name="BKMKReturnFilteredListofUsers"> </a></span></span>

<span data-ttu-id="e1dad-135">透過使用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 和_LdapFilter_或_Filter_參數，您可以輕鬆地傳回一組目標使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e1dad-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="e1dad-136">例如，這個命令會傳回在財務部門中工作的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="e1dad-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="e1dad-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="e1dad-137">Related topics</span></span>
[<span data-ttu-id="e1dad-138">使用 Windows PowerShell 設定商務用 skype online 管理電腦</span><span class="sxs-lookup"><span data-stu-id="e1dad-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


