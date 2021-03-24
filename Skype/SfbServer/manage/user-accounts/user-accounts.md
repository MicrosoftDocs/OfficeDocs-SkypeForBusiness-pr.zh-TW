---
title: 管理商務用 Skype Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文的各節說明如何啟用、暫時停用或移除商務用 Skype Server 中的 Active Directory 使用者。
ms.openlocfilehash: 0cf78b4ebe7023bc5a0f1b4af75c5d9e5a45db1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103119"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="32768-103">管理商務用 Skype Server 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="32768-104">本文的各節說明如何啟用、暫時停用或移除商務用 Skype Server 中的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="32768-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="32768-105">如需如何啟用 Active Directory 使用者的詳細資訊，請參閱 [建立新的使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="32768-105">For information on how to enable an Active Directory user, see [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span></span> <span data-ttu-id="32768-106">如需如何刪除 Active Directory 使用者的詳細資訊，請參閱 [刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="32768-106">For information on how to delete an Active Directory user, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>

<span data-ttu-id="32768-107">當商務用 Skype 使用率最低時，應在維護時段內執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="32768-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="32768-108">在每日或每週排程上進行的工作是否取決於組織的需求。</span><span class="sxs-lookup"><span data-stu-id="32768-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="32768-109">本文包含下列程式：</span><span class="sxs-lookup"><span data-stu-id="32768-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="32768-110">若要搜尋一個或多個使用者</span><span class="sxs-lookup"><span data-stu-id="32768-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="32768-111">新增及啟用新的商務用 Skype Server 使用者</span><span class="sxs-lookup"><span data-stu-id="32768-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="32768-112">停用或重新啟用先前為商務用 Skype Server 啟用的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="32768-113">停用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="32768-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="32768-114">移除具有商務用 Skype Server 管理命令介面的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="32768-115">若要搜尋一個或多個使用者</span><span class="sxs-lookup"><span data-stu-id="32768-115">To search for one or more users</span></span>
<span data-ttu-id="32768-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="32768-116"><a name="Search"> </a></span></span>

<span data-ttu-id="32768-117">您可以使用搜尋查詢的結果，為商務用 Skype 伺服器設定 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="32768-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="32768-118">您可以依顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別元 (URI) 來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="32768-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="32768-119">您可以使用商務用 Skype Server 控制台或 [Active Directory 使用者和電腦] 嵌入式管理單元來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="32768-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="32768-120">下列程式說明如何使用商務用 Skype Server 控制台來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="32768-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="32768-121">在具有中央樹系拓撲的環境中，當您使用使用者的電子郵件地址來搜尋使用者時，搜尋結果可能不准確。</span><span class="sxs-lookup"><span data-stu-id="32768-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="32768-122">您可以改為指定 SIP 位址首碼 (例如 sip:name) 來進行搜尋、新增搜尋篩選並選取包含部分電子郵件位址的 SIP 位址，或使用 **Get-CSUser** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32768-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="32768-123">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="32768-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32768-124">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="32768-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32768-125">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="32768-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32768-126">在 **[搜尋使用者]** 方塊中，輸入您要搜尋之使用者帳戶的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或線路 URI 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="32768-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="32768-127">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="32768-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="32768-128">a.</span><span class="sxs-lookup"><span data-stu-id="32768-128">a.</span></span> <span data-ttu-id="32768-129">按一下畫面右上角就在 **[搜尋結果]** 上方的展開箭頭，然後按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="32768-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="32768-130">b.</span><span class="sxs-lookup"><span data-stu-id="32768-130">b.</span></span> <span data-ttu-id="32768-131">輸入使用者內容，您可以直接輸入文字或是按一下下拉式清單的箭頭以選取使用者內容。</span><span class="sxs-lookup"><span data-stu-id="32768-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="32768-132">c.</span><span class="sxs-lookup"><span data-stu-id="32768-132">c.</span></span> <span data-ttu-id="32768-133">在 **[等於]** 清單中，按一下 **[等於]** 或 **[不等於]**。</span><span class="sxs-lookup"><span data-stu-id="32768-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="32768-134">d.</span><span class="sxs-lookup"><span data-stu-id="32768-134">d.</span></span> <span data-ttu-id="32768-135">在文字方塊中，輸入您要用來篩選搜尋結果的搜尋條件，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="32768-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="32768-p110">搜尋結果會出現在 **[搜尋結果]** 下方。您可以選取清單中任一或全部使用者，然後對所選使用者執行設定工作。</span><span class="sxs-lookup"><span data-stu-id="32768-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="32768-138">新增及啟用新的商務用 Skype Server 使用者</span><span class="sxs-lookup"><span data-stu-id="32768-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="32768-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="32768-139"><a name="Add"> </a></span></span>

<span data-ttu-id="32768-140">在 [Active Directory 使用者及電腦] 中啟用使用者帳戶之後，您可以使用商務用 Skype Server 控制台，將 Active Directory 使用者新增至商務用 Skype Server，以建立及啟用新的商務用 Skype Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="32768-141">您也可以使用 Cmdlet，特別是 [Enable-get-csuser](/powershell/module/skype/enable-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="32768-141">You can also use a cmdlet, specifically [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="32768-142">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="32768-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32768-143">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="32768-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32768-144">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="32768-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32768-145">按一下 **[啟用使用者]**。</span><span class="sxs-lookup"><span data-stu-id="32768-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="32768-146">在 **[新增 Lync Server 使用者]** 對話方塊中，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="32768-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="32768-147">在 [搜尋使用者] 方塊中，輸入您要找的 Active Directory 使用者帳戶的名稱、顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、電子郵件地址、使用者主要名稱 (UPN) 或電話號碼的全部或頭幾個字，然後按一下 [尋找]。</span><span class="sxs-lookup"><span data-stu-id="32768-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="32768-148">在表格中，選取您要新增至商務用 Skype Server 的帳戶，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="32768-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="32768-149">指派使用者至集區、指定其他詳細資料，並指派原則給您要的使用者，然後按一下 **[啟用]**。</span><span class="sxs-lookup"><span data-stu-id="32768-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="32768-150">停用或重新啟用先前為商務用 Skype Server 啟用的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="32768-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="32768-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="32768-152">您可以使用下列程式在商務用 Skype Server 中停用先前啟用的使用者帳戶，而不會丟失您為使用者帳戶所設定的商務用 Skype 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="32768-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="32768-153">因為您不會遺失商務用 Skype Server 使用者帳戶設定，所以您可以重新啟用先前啟用的使用者帳戶，而不需要重新設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="32768-154">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="32768-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32768-155">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="32768-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32768-156">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="32768-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32768-157">在 **[搜尋使用者]** 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或您想要停用或重新啟用的使用者帳戶之線路統一資源識別元 (URI)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="32768-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="32768-158">按一下表中您想要停用或重新啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="32768-159">在 **[動作]** 功能表上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="32768-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="32768-160">若要暫時停用商務用 Skype 伺服器的使用者帳戶，請按一下 [ **暫時停用 Lync server**]。</span><span class="sxs-lookup"><span data-stu-id="32768-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="32768-161">若要啟用商務用 Skype 伺服器的使用者帳戶，請按一下 [ **重新啟用 Lync server**]。</span><span class="sxs-lookup"><span data-stu-id="32768-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="32768-162">使用 Windows Powershell 來停用或重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="32768-163">您可以暫時停用使用者帳戶，然後再使用 **Set-CsUser** Cmdlet 重新啟用使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="32768-164">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32768-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="32768-165">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="32768-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="32768-166">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="32768-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="32768-167">停用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-167">To disable a user account</span></span>

- <span data-ttu-id="32768-168">若要暫時停用使用者帳戶，請將 Enabled 內容值設為 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="32768-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="32768-169">例如：</span><span class="sxs-lookup"><span data-stu-id="32768-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="32768-170">重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-170">To re-enable a user account</span></span>

- <span data-ttu-id="32768-171">若要重新啟用已停用的使用者帳戶，請將 Enabled 內容值設為 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="32768-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="32768-172">例如：</span><span class="sxs-lookup"><span data-stu-id="32768-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="32768-173">如需詳細資訊，請參閱 [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="32768-173">For more information, see the help topic for the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="32768-174">停用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="32768-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="32768-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="32768-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="32768-176">使用下列程式可針對啟用商務用 Skype 伺服器的使用者帳戶停用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="32768-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="32768-177">停用 Enterprise Voice 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="32768-178">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="32768-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32768-179">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="32768-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32768-180">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="32768-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32768-181">在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="32768-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="32768-182">在表格中，按一下您要為 Enterprise Voice 啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="32768-183">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="32768-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="32768-184">在 [ **編輯 Lync Server 使用者** ] 頁面的 [ **電話** 語音] 下，按一下 [ **Enterprise Voice** 以外的任何選項]。</span><span class="sxs-lookup"><span data-stu-id="32768-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32768-185">若要使用 Lync 限制使用者進行音訊或視頻通話，請在 [ **電話語音**] 下，按一下 [ **音訊/視頻已停用**]。</span><span class="sxs-lookup"><span data-stu-id="32768-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="32768-186">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="32768-186">Click **Commit**.</span></span>

<span data-ttu-id="32768-187">使用者現在無法使用 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="32768-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="32768-188">相關資訊：</span><span class="sxs-lookup"><span data-stu-id="32768-188">Related information:</span></span> <br/>[<span data-ttu-id="32768-189">Enterprise Voice 和行動性</span><span class="sxs-lookup"><span data-stu-id="32768-189">Enterprise Voice and mobility</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [<span data-ttu-id="32768-190">在商務用 Skype Server 中啟用使用者的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="32768-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="32768-191">商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="32768-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="32768-192">移除具有商務用 Skype Server 管理命令介面的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="32768-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="32768-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="32768-194">您可以使用下列程式，在商務用 Skype Server 中移除之前新增的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="32768-195">移除使用者會造成您遺失該使用者的所有設定。</span><span class="sxs-lookup"><span data-stu-id="32768-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="32768-196">若要暫時停用使用者帳戶，請參閱 [停用或重新啟用先前為商務用 Skype Server 啟用的使用者帳戶](user-accounts.md#Disable)。</span><span class="sxs-lookup"><span data-stu-id="32768-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="32768-197">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="32768-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="32768-198">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="32768-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="32768-199">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="32768-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="32768-200">在 [搜尋使用者] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或您想要停用或重新啟用的使用者帳戶之線路統一資源識別元 (URI)，然後按一下 [尋找]。</span><span class="sxs-lookup"><span data-stu-id="32768-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="32768-201">在表中按一下您想要移除的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="32768-202">選取 [動作] 功能表中的 [從 Lync Server 移除]，隨即顯示對話方塊。</span><span class="sxs-lookup"><span data-stu-id="32768-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="32768-203">選取對話方塊中的 [確定] 以移除使用者。</span><span class="sxs-lookup"><span data-stu-id="32768-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="32768-204">使用 Windows Powershell Cmdlet 移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="32768-205">您可以使用 Disable-CsUser Cmdlet 來移除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32768-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="32768-206">您可以從商務用 Skype Server 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32768-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="32768-207">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="32768-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="32768-208">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="32768-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="32768-209">移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="32768-209">To remove a user account</span></span>
<span data-ttu-id="32768-210">若要移除使用者帳戶，請使用 Disable-CsUser Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32768-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="32768-211">例如：</span><span class="sxs-lookup"><span data-stu-id="32768-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="32768-212">如需詳細資訊，請參閱 [get-csuser 指令程式](/powershell/module/skype/disable-csuser?view=skype-ps) 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="32768-212">For more information, see the help topic for the [Disable-CsUser](/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="32768-213">另請參閱</span><span class="sxs-lookup"><span data-stu-id="32768-213">See also</span></span>
<span data-ttu-id="32768-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="32768-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="32768-215">Enable-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="32768-215">Enable-CsUser</span></span>](/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="32768-216">停用 Get-csuser</span><span class="sxs-lookup"><span data-stu-id="32768-216">Disable-CsUser</span></span>](/powershell/module/skype/disable-csuser?view=skype-ps)