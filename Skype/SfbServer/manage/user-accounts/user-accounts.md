---
title: 管理商務用 Skype Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的各節說明如何啟用、暫時停用或移除商務用 Skype Server 中的 Active Directory 使用者。
ms.openlocfilehash: 83ab64415b21d37f12d3768feeb39b11491787af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187069"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="24800-103">管理商務用 Skype Server 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="24800-104">本文中的各節說明如何啟用、暫時停用或移除商務用 Skype Server 中的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="24800-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="24800-105">如需如何啟用 Active Directory 使用者的相關資訊, 請參閱[建立新的使用者帳戶](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="24800-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="24800-106">如需如何刪除 Active Directory 使用者的相關資訊, 請參閱[刪除使用者帳戶](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="24800-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="24800-107">當商務用 Skype 使用為最低時, 這些程式應該在 [維護] 視窗中執行。</span><span class="sxs-lookup"><span data-stu-id="24800-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="24800-108">無論是在每天或每週排程上完成, 都將由貴組織的需求決定。</span><span class="sxs-lookup"><span data-stu-id="24800-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="24800-109">本文包含下列程式:</span><span class="sxs-lookup"><span data-stu-id="24800-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="24800-110">搜尋一或多位使用者</span><span class="sxs-lookup"><span data-stu-id="24800-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="24800-111">新增並啟用新的商務用 Skype Server 使用者</span><span class="sxs-lookup"><span data-stu-id="24800-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="24800-112">停用或重新啟用先前針對商務用 Skype Server 啟用的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="24800-113">停用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="24800-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="24800-114">使用商務用 Skype Server Management Shell 移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="24800-115">搜尋一或多位使用者</span><span class="sxs-lookup"><span data-stu-id="24800-115">To search for one or more users</span></span>
<span data-ttu-id="24800-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="24800-116"></span></span>

<span data-ttu-id="24800-117">您可以使用搜尋查詢的結果來設定商務用 Skype Server 的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="24800-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="24800-118">您可以依顯示名稱、名字、姓氏、安全帳戶管理員 (SAM) 帳戶名稱、SIP 位址或行統一資源識別項 (URI) 來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="24800-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="24800-119">您可以使用商務用 Skype Server 的 [控制台] 或 [Active Directory 使用者和電腦] 管理單元來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="24800-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="24800-120">下列程式說明如何使用商務用 Skype Server 的 [控制台] 來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="24800-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="24800-121">在具有中央林拓撲的環境中, 當您使用使用者的電子郵件地址搜尋使用者時, 搜尋結果可能不正確。</span><span class="sxs-lookup"><span data-stu-id="24800-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="24800-122">相反地, 您可以透過指定 SIP 位址首碼 (例如 sip: name、新增搜尋篩選器, 然後選取包含部分電子郵件地址的 SIP 位址) 來搜尋使用者, 或使用**move-csuser** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24800-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="24800-123">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="24800-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="24800-124">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="24800-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="24800-125">在左側導覽列中, 按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="24800-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="24800-126">在 [**搜尋使用者**] 方塊中, 輸入您要搜尋之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或行 URI, 然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="24800-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="24800-127">可選指定額外的搜尋準則以縮小結果範圍:</span><span class="sxs-lookup"><span data-stu-id="24800-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="24800-128">是.</span><span class="sxs-lookup"><span data-stu-id="24800-128">a.</span></span> <span data-ttu-id="24800-129">按一下 [**搜尋結果**] 上方畫面右上角的展開箭號按鈕, 然後按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="24800-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="24800-130">乙.</span><span class="sxs-lookup"><span data-stu-id="24800-130">b.</span></span> <span data-ttu-id="24800-131">輸入使用者屬性或按一下下拉式清單中的箭號, 以選取使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="24800-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="24800-132">c-clip.</span><span class="sxs-lookup"><span data-stu-id="24800-132">c.</span></span> <span data-ttu-id="24800-133">在 [**等於**] 清單中, 按一下 [**等於**或**不等於**]。</span><span class="sxs-lookup"><span data-stu-id="24800-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="24800-134">希望.</span><span class="sxs-lookup"><span data-stu-id="24800-134">d.</span></span> <span data-ttu-id="24800-135">在文字方塊中, 輸入您要用來篩選搜尋結果的搜尋準則, 然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="24800-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="24800-136">搜尋結果會顯示在 [**搜尋結果**] 下。</span><span class="sxs-lookup"><span data-stu-id="24800-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="24800-137">您可以選取清單中的任何或所有使用者, 並在您選取的使用者上執行設定工作。</span><span class="sxs-lookup"><span data-stu-id="24800-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="24800-138">新增並啟用新的商務用 Skype Server 使用者</span><span class="sxs-lookup"><span data-stu-id="24800-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="24800-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="24800-139"></span></span>

<span data-ttu-id="24800-140">在 Active Directory 使用者和電腦中啟用使用者帳戶之後, 您就可以使用商務用 Skype Server 的 [控制台], 透過將 Active Directory 使用者新增至商務用 Skype 伺服器來建立並啟用新的商務用 Skype Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="24800-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="24800-141">您也可以使用 Cmdlet, 特別是[Enable-move-csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="24800-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="24800-142">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="24800-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="24800-143">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="24800-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="24800-144">在左側導覽列中, 按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="24800-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="24800-145">按一下 [**啟用使用者**]。</span><span class="sxs-lookup"><span data-stu-id="24800-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="24800-146">在 [**新的 Lync Server 使用者**] 對話方塊\*\*\*\* 中, 按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="24800-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="24800-147">在 [**搜尋使用者**] 方塊中, 輸入名稱、顯示名稱、名字、姓氏、安全帳戶管理員 (SAM) 帳戶名稱、電子郵件地址、使用者主體名稱 (UPN), 或您想要的 Active Directory 使用者帳戶的電話號碼。, 然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="24800-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="24800-148">在表格中, 選取您要新增至商務用 Skype Server 的帳戶, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="24800-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="24800-149">將使用者指派至 [泳池], 指定任何其他詳細資料, 然後將原則指派給您想要的使用者, 然後按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="24800-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="24800-150">停用或重新啟用先前針對商務用 Skype Server 啟用的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="24800-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="24800-151"></span></span>

<span data-ttu-id="24800-152">您可以使用下列程式, 在商務用 Skype Server 中停用先前啟用的使用者帳戶, 而不會遺失您針對使用者帳戶所設定的商務用 Skype 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="24800-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="24800-153">因為您不會遺失商務用 Skype Server 的使用者帳戶設定, 所以您可以重新啟用先前已啟用的使用者帳戶, 而不需重新設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="24800-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="24800-154">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="24800-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="24800-155">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="24800-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="24800-156">在左側導覽列中, 按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="24800-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="24800-157">在 [**搜尋使用者**] 方塊中, 輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員 (SAM) 帳戶名稱、SIP 位址或行統一資源識別項 (URI)。然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="24800-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="24800-158">在表格中, 按一下您要停用或重新啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="24800-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="24800-159">在 [**動作**] 功能表上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="24800-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="24800-160">若要暫時停用商務用 Skype Server 的使用者帳戶, 請按一下 [**針對 Lync Server 暫時停**用]。</span><span class="sxs-lookup"><span data-stu-id="24800-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="24800-161">若要啟用商務用 Skype Server 的使用者帳戶, 請按一下 [**針對 Lync Server 重新啟用**]。</span><span class="sxs-lookup"><span data-stu-id="24800-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="24800-162">使用 Windows Powershell 來停用或重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="24800-163">使用者帳戶可以暫時停用, 稍後再使用**move-csuser** Cmdlet 重新啟用。</span><span class="sxs-lookup"><span data-stu-id="24800-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="24800-164">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24800-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="24800-165">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="24800-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="24800-166">在商務用 Skype 伺服器中, 程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="24800-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="24800-167">停用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-167">To disable a user account</span></span>

- <span data-ttu-id="24800-168">若要暫時停用使用者帳戶, 請將 Enabled 屬性的值設為 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="24800-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="24800-169">例如：</span><span class="sxs-lookup"><span data-stu-id="24800-169">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="24800-170">若要重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-170">To re-enable a user account</span></span>

- <span data-ttu-id="24800-171">若要重新啟用已停用的使用者帳戶, 請將 Enabled 屬性的值設定為 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="24800-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="24800-172">例如：</span><span class="sxs-lookup"><span data-stu-id="24800-172">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="24800-173">如需詳細資訊, 請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="24800-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="24800-174">停用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="24800-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="24800-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="24800-175"></span></span>

<span data-ttu-id="24800-176">使用下列程式來停用商務用 Skype Server 啟用的使用者帳戶的企業語音。</span><span class="sxs-lookup"><span data-stu-id="24800-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="24800-177">針對企業語音停用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="24800-178">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="24800-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="24800-179">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="24800-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="24800-180">在左側導覽列中, 按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="24800-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="24800-181">在 [**搜尋使用者**] 方塊中, 輸入您要啟用之使用者帳戶的全部或部分的顯示名稱、名字、姓氏、安全帳戶管理員 (SAM) 帳戶名稱、SIP 位址或行統一資源識別項 (URI), 然後按一下[**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="24800-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="24800-182">在表格中, 按一下您要為企業語音啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="24800-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="24800-183">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="24800-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="24800-184">在 [**編輯 Lync Server 使用者**] 頁面的 [**電話**] 底下, 按一下 [**企業語音**] 以外的任何選項。</span><span class="sxs-lookup"><span data-stu-id="24800-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24800-185">若要使用 Lync 限制使用者進行音訊或視頻通話, 請在 [**電話**] 底下, 按一下 [**音訊/視頻已停用**]。</span><span class="sxs-lookup"><span data-stu-id="24800-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="24800-186">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="24800-186">Click **Commit**.</span></span>

<span data-ttu-id="24800-187">使用者現在無法使用企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="24800-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="24800-188">相關資訊:</span><span class="sxs-lookup"><span data-stu-id="24800-188">Related information:</span></span> <br/>[<span data-ttu-id="24800-189">企業語音與行動性</span><span class="sxs-lookup"><span data-stu-id="24800-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="24800-190">在商務用 Skype Server 中啟用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="24800-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="24800-191">商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="24800-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="24800-192">使用商務用 Skype Server Management Shell 移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="24800-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="24800-193"></span></span>

<span data-ttu-id="24800-194">您可以使用下列程式, 在商務用 Skype Server 中移除先前新增的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="24800-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="24800-195">移除使用者將會導致您遺失任何您為使用者帳戶所設定的設定。</span><span class="sxs-lookup"><span data-stu-id="24800-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="24800-196">如果您想改為暫時停用使用者帳戶, 請參閱[停用或重新啟用先前針對商務用 Skype Server 啟用的使用者帳戶](user-accounts.md#Disable)。</span><span class="sxs-lookup"><span data-stu-id="24800-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="24800-197">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="24800-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="24800-198">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="24800-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="24800-199">在左側導覽列中, 按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="24800-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="24800-200">在 [**搜尋使用者**] 方塊中, 輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員 (SAM) 帳戶名稱、SIP 位址或行統一資源識別項 (URI)。然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="24800-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="24800-201">在表格中, 按一下您要移除的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="24800-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="24800-202">在 [**動作**] 功能表上, 選取 [**從 Lync Server 移除**], 隨後便會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="24800-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="24800-203">從對話方塊中, 選取 **[確定]** 以移除使用者。</span><span class="sxs-lookup"><span data-stu-id="24800-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="24800-204">使用 Windows Powershell Cmdlet 移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="24800-205">您可以使用 Disable Move-csuser Cmdlet 來移除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="24800-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="24800-206">此 Cmdlet 可從商務用 Skype Server Management 命令介面或從遠端會話 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="24800-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="24800-207">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="24800-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="24800-208">在商務用 Skype 伺服器中, 程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="24800-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="24800-209">移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="24800-209">To remove a user account</span></span>
<span data-ttu-id="24800-210">若要移除使用者帳戶, 請使用 Disable-Move-csuser Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24800-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="24800-211">例如：</span><span class="sxs-lookup"><span data-stu-id="24800-211">For example:</span></span>

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="24800-212">如需詳細資訊, 請參閱[Disable move-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="24800-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="24800-213">另請參閱</span><span class="sxs-lookup"><span data-stu-id="24800-213">See also</span></span>
<span data-ttu-id="24800-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="24800-214"></span></span>

[<span data-ttu-id="24800-215">Enable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="24800-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="24800-216">Disable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="24800-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
