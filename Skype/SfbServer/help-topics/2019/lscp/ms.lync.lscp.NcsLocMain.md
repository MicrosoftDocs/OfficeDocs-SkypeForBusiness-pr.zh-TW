---
title: 位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: 位置原則決定是否啟用增強型 9-1-1 (E9-1-1) 及其使用方式，以及針對使用者和連絡人使用位置資訊的方式。
ms.openlocfilehash: e86bf3c37350f0e7e571068eb276aa0b237dc86c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192130"
---
# <a name="location-policy"></a><span data-ttu-id="4bb6f-103">位置原則</span><span class="sxs-lookup"><span data-stu-id="4bb6f-103">Location Policy</span></span>

<span data-ttu-id="4bb6f-104">位置原則決定是否啟用增強型 9-1-1 (E9-1-1) 及其使用方式，以及針對使用者和連絡人使用位置資訊的方式。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="4bb6f-105">位置原則包含全域原則，也可能會包含一或多項網站與使用者原則：</span><span class="sxs-lookup"><span data-stu-id="4bb6f-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="4bb6f-106">**全域原則:** 預設會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="4bb6f-107">您可以編輯全域原則, 但無法將其刪除。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="4bb6f-108">如果您嘗試移除全域原則, 所有設定都將重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="4bb6f-109">**網站原則 (選用):** 您可以建立一或多個網站位置原則, 每個都適用于特定網站。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="4bb6f-110">網站原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="4bb6f-111">**使用者原則 (選用):** 您可以建立一或多個使用者位置原則, 每個都適用于特定的使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="4bb6f-112">使用者原則會覆寫全域原則和網站原則。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="4bb6f-113">您也可以指派位置原則給網站 (即子網路群組)。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="4bb6f-114">指派給網站的位置原則，優先於其他所有使用者原則。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="4bb6f-115">如需使用 Cmdlet 將位置原則指派給網路網站的詳細資料, 請參閱[在商務用 Skype Server 中新增位置原則至網路網站](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="4bb6f-116">如需使用商務用 Skype Server [控制台] 將位置原則指派給網路網站的詳細資料, 請參閱設定[網路網站](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="4bb6f-117">「位置原則」\*\*\*\* 頁面會顯示為您組織所定義之所有位置原則的清單。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4bb6f-118">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="4bb6f-118">Tasks you can perform</span></span>

<span data-ttu-id="4bb6f-119">您可以從「位置原則」\*\*\*\* 頁面執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="4bb6f-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="4bb6f-120">建立新的網站位置原則或使用者位置原則</span><span class="sxs-lookup"><span data-stu-id="4bb6f-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="4bb6f-121">變更全域原則或現有的網站原則或使用者原則</span><span class="sxs-lookup"><span data-stu-id="4bb6f-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="4bb6f-122">刪除網站原則或使用者原則</span><span class="sxs-lookup"><span data-stu-id="4bb6f-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4bb6f-123">UI 參考</span><span class="sxs-lookup"><span data-stu-id="4bb6f-123">UI Reference</span></span>

<span data-ttu-id="4bb6f-124">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="4bb6f-125">**新增**啟動新的網站位置原則或使用者位置原則。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="4bb6f-126">[**編輯**]開啟所選的位置原則以進行編輯、選取清單中的所有位置原則, 或刪除選取的網站原則或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4bb6f-127">**刪除**   會將全域原則的設定重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="4bb6f-128">**更新**刷新位置原則的清單。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="4bb6f-129">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="4bb6f-130">**名稱**識別位置原則。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="4bb6f-131">**範圍**識別位置原則的範圍: [全域]、[網站] 或 [使用者]。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="4bb6f-132">**E9-1-1**已檢查是否已針對 E9-1-1 啟用指派此位置原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="4bb6f-133">**位置**指定使用者在新位置使用商務用 Skype Server 登錄時, 是否提示使用者輸入位置資訊, 以及他們是否在沒有輸入位置資訊的情況下關閉提示時, 才會看到免責聲明。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="4bb6f-134">**PSTN 使用量**指定公用的交換電話網絡 (PSTN) 用法, 用來判斷用來從使用這個設定檔的用戶端路由緊急呼叫的語音路線。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="4bb6f-135">**E9-1-1 個數字**指定要撥打緊急服務的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="4bb6f-136">**E9-1-1 蒙板**指定使用者撥號的號碼, 然後將它轉換成緊急電話撥號碼。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="4bb6f-137">如需企業語音緊急服務功能和功能的詳細資訊, 請參閱規劃檔中的[E9-1-](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 1。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="4bb6f-138">如需使用位置原則的詳細資訊，請參閱作業文件中的〈[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="4bb6f-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


