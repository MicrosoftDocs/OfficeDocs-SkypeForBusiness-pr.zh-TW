---
title: 在商務用 Skype 用戶端中設定智慧連絡人清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：瞭解如何在商務用 Skype 用戶端中開啟智慧連絡人清單功能。
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095797"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="bbd79-103">在商務用 Skype 用戶端中設定智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="bbd79-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="bbd79-104">**摘要：** 瞭解如何在商務用 Skype 用戶端中開啟智慧連絡人清單功能。</span><span class="sxs-lookup"><span data-stu-id="bbd79-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="bbd79-105">[智慧連絡人清單] 功能可讓您的使用者自動填入連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="bbd79-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="bbd79-106">在您第一次使用商務用 Skype 時，您的使用者將會自動查看其主管和其小組中的其他人員。</span><span class="sxs-lookup"><span data-stu-id="bbd79-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="bbd79-107">Microsoft 365 和 Office 365 使用者預設會開啟此功能，但您必須透過設定用戶端原則設定，明確為您的內部部署使用者啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="bbd79-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="bbd79-108">設定此功能時，請牢記下列事項：</span><span class="sxs-lookup"><span data-stu-id="bbd79-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="bbd79-109">使用者最多13個會依下列順序自動新增至 [智慧連絡人] 清單：</span><span class="sxs-lookup"><span data-stu-id="bbd79-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="bbd79-110">管理員</span><span class="sxs-lookup"><span data-stu-id="bbd79-110">Manager</span></span>

  2. <span data-ttu-id="bbd79-111">依字母順序指示</span><span class="sxs-lookup"><span data-stu-id="bbd79-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="bbd79-112">對等字母順序</span><span class="sxs-lookup"><span data-stu-id="bbd79-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="bbd79-113">當使用者第一次登入時，就會建立新的群組，名稱為 My Group。</span><span class="sxs-lookup"><span data-stu-id="bbd79-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="bbd79-114">根據在 [管理員] 欄位中填入的使用者別名，群組會自動填入使用者的 AD 群組關聯中的人員。</span><span class="sxs-lookup"><span data-stu-id="bbd79-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="bbd79-115">請注意，對 AD 群組成員資格的變更不會對最初填入的群組進行更新。</span><span class="sxs-lookup"><span data-stu-id="bbd79-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="bbd79-116">若使用者刪除連絡人或群組，就不會重新建立連絡人或群組。</span><span class="sxs-lookup"><span data-stu-id="bbd79-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="bbd79-117">如果開啟自動標記，清單中的連絡人將會標示為「顯示狀態變更」。</span><span class="sxs-lookup"><span data-stu-id="bbd79-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="bbd79-118">自動標記預設為開啟狀態，但您可以選擇將它關閉。</span><span class="sxs-lookup"><span data-stu-id="bbd79-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="bbd79-119">群組中的所有新使用者都會收到已新增至 [連絡人] 清單中的通知。</span><span class="sxs-lookup"><span data-stu-id="bbd79-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="bbd79-120">使用者可以手動將新成員新增至其「我的群組」或其選擇的其他群組。</span><span class="sxs-lookup"><span data-stu-id="bbd79-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="bbd79-121">此功能僅適用于第一次登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="bbd79-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="bbd79-122">如果使用者先前已從任何裝置登入，例如，任何行動裝置或 Mac--沒有為該使用者啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="bbd79-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="bbd79-123">設定智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="bbd79-123">Configure Smart contacts list</span></span>

<span data-ttu-id="bbd79-124">若要為您的使用者啟用 [智慧連絡人清單] 功能，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bbd79-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="bbd79-125">建立新的 CsClientPolicy 專案，並將其新增至全域用戶端原則。</span><span class="sxs-lookup"><span data-stu-id="bbd79-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="bbd79-126">請確定 [通訊錄] 搜尋只針對 Web 搜尋設定。</span><span class="sxs-lookup"><span data-stu-id="bbd79-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="bbd79-127">建立原則專案以啟用智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="bbd79-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="bbd79-128">若要建立原則專案以啟用智慧連絡人清單功能，請將 [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) Cmdlet 與 EnableClientAutoPopulateWithTeam 選項搭配使用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbd79-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="bbd79-129">接下來，使用 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet，將變更寫入全域原則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbd79-129">Next, use the [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="bbd79-130">您可以選擇性地建立原則來關閉自動標記，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbd79-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="bbd79-131">您也必須將對應原則的 AddressBookAvailability 參數設定為 WebSearchOnly。</span><span class="sxs-lookup"><span data-stu-id="bbd79-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="bbd79-132">如需詳細資訊，請參閱 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="bbd79-132">For more information, see [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="bbd79-133">疑難排解</span><span class="sxs-lookup"><span data-stu-id="bbd79-133">Troubleshoot</span></span>

<span data-ttu-id="bbd79-134">如果智慧連絡人清單未如預期運作，請檢查下列各項：</span><span class="sxs-lookup"><span data-stu-id="bbd79-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="bbd79-135">驗證設定。</span><span class="sxs-lookup"><span data-stu-id="bbd79-135">Validate the configuration.</span></span> 

- <span data-ttu-id="bbd79-136">確認已填入 AD 組織資訊。</span><span class="sxs-lookup"><span data-stu-id="bbd79-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="bbd79-137">在新的使用者上收集商務用 Skype 用戶端記錄以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="bbd79-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="bbd79-138">確認商務用 Skype 用戶端 UI 不會顯示無法連接到通訊錄的訊息。</span><span class="sxs-lookup"><span data-stu-id="bbd79-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="bbd79-139">若要確認通訊錄連通性，請在商務用 Skype 用戶端搜尋列中執行使用者搜尋。</span><span class="sxs-lookup"><span data-stu-id="bbd79-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="bbd79-140">當使用者第一次登入商務用 Skype 時，AD DS 複寫問題可能會導致連絡人無法解析。</span><span class="sxs-lookup"><span data-stu-id="bbd79-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>