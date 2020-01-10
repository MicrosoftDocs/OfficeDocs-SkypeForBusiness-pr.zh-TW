---
title: 在商務用 Skype 用戶端中設定智慧連絡人清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：瞭解如何在商務用 Skype 用戶端中開啟 [智慧連絡人清單] 功能。
ms.openlocfilehash: 4c867232fd07131666033dc48ff9930dcdf6dccb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002683"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="acdd3-103">在商務用 Skype 用戶端中設定智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="acdd3-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="acdd3-104">**摘要：** 瞭解如何在商務用 Skype 用戶端中開啟 [智慧連絡人清單] 功能。</span><span class="sxs-lookup"><span data-stu-id="acdd3-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="acdd3-105">[智慧連絡人清單] 功能可讓您的使用者自動填入連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="acdd3-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="acdd3-106">在您第一次使用商務用 Skype 時，您的使用者會自動看到其小組中的主管及其他人。</span><span class="sxs-lookup"><span data-stu-id="acdd3-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="acdd3-107">預設會針對 Office 365 使用者開啟這項功能，但您必須透過設定用戶端原則設定，為您的內部部署使用者明確啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="acdd3-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="acdd3-108">設定此功能時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="acdd3-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="acdd3-109">使用者（最多13個）會自動新增到 [智慧連絡人] 清單中，順序如下：</span><span class="sxs-lookup"><span data-stu-id="acdd3-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="acdd3-110">R</span><span class="sxs-lookup"><span data-stu-id="acdd3-110">Manager</span></span>

  2. <span data-ttu-id="acdd3-111">依字母順序定向</span><span class="sxs-lookup"><span data-stu-id="acdd3-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="acdd3-112">對等依字母順序排列</span><span class="sxs-lookup"><span data-stu-id="acdd3-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="acdd3-113">使用者第一次登入時，就會建立一個名為「我的群組」的新群組。</span><span class="sxs-lookup"><span data-stu-id="acdd3-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="acdd3-114">群組會根據 [管理員] 欄位中填入的使用者別名，自動填入使用者的 AD 群組關係中的人員。</span><span class="sxs-lookup"><span data-stu-id="acdd3-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="acdd3-115">請注意，在最初填入群組之後，變更 AD 群組成員資格不會導致更新到我的群組。</span><span class="sxs-lookup"><span data-stu-id="acdd3-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="acdd3-116">如果使用者刪除連絡人或群組，則不會重新建立連絡人與群組。</span><span class="sxs-lookup"><span data-stu-id="acdd3-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="acdd3-117">如果已開啟 [自動標記]，清單中的連絡人將會標記為 [目前狀態變更]。</span><span class="sxs-lookup"><span data-stu-id="acdd3-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="acdd3-118">自動標記功能預設為開啟狀態，但您可以選擇將它關閉。</span><span class="sxs-lookup"><span data-stu-id="acdd3-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="acdd3-119">群組中的所有新使用者都會收到已新增至 [連絡人] 清單的資訊。</span><span class="sxs-lookup"><span data-stu-id="acdd3-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="acdd3-120">使用者可以手動將新成員新增到他們的群組，或其他他們選擇的群組。</span><span class="sxs-lookup"><span data-stu-id="acdd3-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="acdd3-121">此功能僅適用于第一次登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="acdd3-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="acdd3-122">如果使用者先前已從任何裝置登入，包括（例如，任何行動裝置或 Mac），則該使用者沒有啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="acdd3-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="acdd3-123">設定智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="acdd3-123">Configure Smart contacts list</span></span>

<span data-ttu-id="acdd3-124">若要為使用者啟用 [智慧連絡人清單] 功能，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="acdd3-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="acdd3-125">建立新的 CsClientPolicy 專案，然後將它新增到全域用戶端原則。</span><span class="sxs-lookup"><span data-stu-id="acdd3-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="acdd3-126">請確定 [通訊錄搜尋] 只設定為 [網頁搜尋]。</span><span class="sxs-lookup"><span data-stu-id="acdd3-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="acdd3-127">建立原則專案以啟用智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="acdd3-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="acdd3-128">若要建立原則專案以啟用智慧連絡人清單功能，請使用[CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) Cmdlet 與 EnableClientAutoPopulateWithTeam 選項，如下所示：</span><span class="sxs-lookup"><span data-stu-id="acdd3-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="acdd3-129">接著，使用[CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet，將變更寫入全域原則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="acdd3-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="acdd3-130">您也可以選擇建立原則來關閉自動標記，如下所示：</span><span class="sxs-lookup"><span data-stu-id="acdd3-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="acdd3-131">您也必須將對應原則的 AddressBookAvailability 參數設定為 WebSearchOnly。</span><span class="sxs-lookup"><span data-stu-id="acdd3-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="acdd3-132">如需詳細資訊，請參閱[設定 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="acdd3-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="acdd3-133">疑難排解</span><span class="sxs-lookup"><span data-stu-id="acdd3-133">Troubleshoot</span></span>

<span data-ttu-id="acdd3-134">如果智慧連絡人清單無法正常運作，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="acdd3-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="acdd3-135">驗證設定。</span><span class="sxs-lookup"><span data-stu-id="acdd3-135">Validate the configuration.</span></span> 

- <span data-ttu-id="acdd3-136">確認已填入廣告組織資訊。</span><span class="sxs-lookup"><span data-stu-id="acdd3-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="acdd3-137">收集新使用者的商務用 Skype 用戶端記錄，以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="acdd3-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="acdd3-138">確認商務用 Skype 用戶端 UI 不會顯示無法連接至通訊錄的訊息。</span><span class="sxs-lookup"><span data-stu-id="acdd3-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="acdd3-139">若要確認通訊錄連通性，請在商務用 Skype 用戶端搜尋列中執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="acdd3-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="acdd3-140">當使用者第一次登入商務用 Skype 時，AD DS 複製問題可能會導致連絡人無法解析。</span><span class="sxs-lookup"><span data-stu-id="acdd3-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


