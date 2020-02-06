---
title: 自訂商務用 Skype Server 的使用者帳戶屬性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本節中的程式來修改個別的使用者帳戶屬性。
ms.openlocfilehash: 96885a1f24685eccc85469209dd36ad655c80fed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817063"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="1cc20-103">自訂商務用 Skype Server 的使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="1cc20-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="1cc20-104">您可以使用本節中的程式來修改個別的使用者帳戶屬性。</span><span class="sxs-lookup"><span data-stu-id="1cc20-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="1cc20-105">您可以在個別使用者層級完成兩個基本作業：</span><span class="sxs-lookup"><span data-stu-id="1cc20-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="1cc20-106">針對特定的使用者帳戶設定電話選項</span><span class="sxs-lookup"><span data-stu-id="1cc20-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="1cc20-107">將使用者移至另一個資源區</span><span class="sxs-lookup"><span data-stu-id="1cc20-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="1cc20-108">針對特定的使用者帳戶設定電話選項</span><span class="sxs-lookup"><span data-stu-id="1cc20-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="1cc20-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="1cc20-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="1cc20-110">您可以自訂特定使用者的電話設定（只要個別使用者已啟用商務用 Skype 伺服器且組織支援電話語音）。</span><span class="sxs-lookup"><span data-stu-id="1cc20-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="1cc20-111">商務用 Skype Server 使用者電話選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="1cc20-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="1cc20-112">**音訊/視頻已停用**使用者無法使用音訊和影片進行通話。</span><span class="sxs-lookup"><span data-stu-id="1cc20-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="1cc20-113">**僅限 pc 至電腦**使用者只能進行 PC 對電腦音訊或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="1cc20-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="1cc20-114">**企業語音**使用者可以使用商務用 Skype 伺服器基礎結構來傳送所有來電和撥出電話。</span><span class="sxs-lookup"><span data-stu-id="1cc20-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="1cc20-115">使用者也可以進行 PC 對電腦通話。</span><span class="sxs-lookup"><span data-stu-id="1cc20-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="1cc20-116">**遠端通話控制**使用者可以使用商務用 Skype Server 來控制桌面電話，也可以進行 PC 對電腦通話。</span><span class="sxs-lookup"><span data-stu-id="1cc20-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="1cc20-117">如需有關為組織設定電話語音的詳細資訊，請參閱在[商務用 Skype server 中啟用企業語音的使用者](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)，以及在部署檔中[部署商務用 skype 伺服器中的企業語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc20-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="1cc20-118">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1cc20-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1cc20-119">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1cc20-120">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="1cc20-121">在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="1cc20-122">在表格中，按一下您要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1cc20-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="1cc20-123">按一下 [**編輯**] 功能表上的 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="1cc20-124">在 [**電話**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1cc20-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="1cc20-125">若要停用使用者的音訊和視頻通話，請按一下 [**音訊/視頻停用**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="1cc20-126">若要為使用者啟用 PC 對電腦音訊通訊，但不啟用遠端通話控制或企業語音，請按一下 [**僅電腦至電腦**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="1cc20-127">針對使用者在 pc 對電腦音訊通訊所用的電話，指定**行 URI**的值。</span><span class="sxs-lookup"><span data-stu-id="1cc20-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="1cc20-128">若要使用商務用 Skype 基礎結構來傳送使用者的電話，請依照服務類別（包括 PC 對電腦音訊通訊），按一下 [**企業語音**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="1cc20-129">在 [**行 URI**] 中，指定企業語音的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1cc20-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="1cc20-130">在 [**撥號計畫原則**] 和 [**語音原則**] 中，為使用者指定適當的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc20-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="1cc20-131">若要指定將使用者撥打的電話號碼轉換為 e. 164 格式的正常化規則，請在**位置原則**中選取適當的位置設定檔。</span><span class="sxs-lookup"><span data-stu-id="1cc20-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="1cc20-132">若要啟用遠端通話控制，讓使用者能夠從商務用 Skype 伺服器控制其桌面電話線路，以進行 PC 對電腦通話和 PC 到電話的通話，請按一下 [**遠端通話控制**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="1cc20-133">在 [**行 URI**] 中，指定遠端通話控制的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1cc20-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="1cc20-134">使用者必須有桌面手機和私人分支 exchange （PBX）連線才能進行呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="1cc20-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="1cc20-135">將使用者移至另一個資源區</span><span class="sxs-lookup"><span data-stu-id="1cc20-135">Move users to another pool</span></span>
<span data-ttu-id="1cc20-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="1cc20-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="1cc20-137">您可以使用商務用 Skype Server 的 [控制台]，將使用者指派給特定的伺服器或文件庫。</span><span class="sxs-lookup"><span data-stu-id="1cc20-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="1cc20-138">將所有現有使用者從執行 Lync Server 2010 或較舊版本的來源池移至複雜的 Active Directory 環境中的商務用 Skype Server 目標池，可能會導致較慢的 Active Directory 複製。</span><span class="sxs-lookup"><span data-stu-id="1cc20-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="1cc20-139">若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或較舊版本的 pool 中移動使用者，或者您可以使用商務用 Skype Server Management Shell，以使用 Cmdlet 來移動使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc20-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="1cc20-140">此外，篩選功能也可與商務用 Skype 伺服器使用者搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1cc20-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="1cc20-141">若要將選取的使用者移至不同的伺服器或文件庫</span><span class="sxs-lookup"><span data-stu-id="1cc20-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="1cc20-142">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1cc20-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1cc20-143">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="1cc20-144">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="1cc20-145">在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="1cc20-146">在表格中，選取清單中特定的使用者或使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc20-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="1cc20-147">在 [**動作**] 功能表上，按一下 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="1cc20-148">在 [**移動使用者**] 中，選取您要在 [**目的地註冊機構**] 中將使用者移至哪個池。</span><span class="sxs-lookup"><span data-stu-id="1cc20-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="1cc20-149">可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cc20-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="1cc20-150">如果您選取 [**強制**]，使用者帳戶就會移動，但任何相關聯的使用者資料都會被刪除（例如，使用者已排程的會議）。</span><span class="sxs-lookup"><span data-stu-id="1cc20-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="1cc20-151">如果您不選取它，就會移動帳戶和相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="1cc20-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="1cc20-152">將所有使用者從一個伺服器或文檔池移至另一個伺服器或文檔池中</span><span class="sxs-lookup"><span data-stu-id="1cc20-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="1cc20-153">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1cc20-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1cc20-154">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="1cc20-155">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="1cc20-156">在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="1cc20-157">在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。</span><span class="sxs-lookup"><span data-stu-id="1cc20-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="1cc20-158">在 [**目的地註冊機構] 池中**，選取您要將使用者移至哪個池。</span><span class="sxs-lookup"><span data-stu-id="1cc20-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="1cc20-159">可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cc20-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="1cc20-160">如果您選取 [**強制**]，使用者帳戶就會移動，但任何相關聯的使用者資料都會被刪除（例如，使用者已排程的會議）。</span><span class="sxs-lookup"><span data-stu-id="1cc20-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="1cc20-161">如果您不選取它，就會移動帳戶和相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="1cc20-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="1cc20-162">使用篩選將使用者從一個池中移到另一個池</span><span class="sxs-lookup"><span data-stu-id="1cc20-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="1cc20-163">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1cc20-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1cc20-164">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1cc20-165">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="1cc20-166">在 [**使用者搜尋**] 中，按一下 [**搜尋**]，然後按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="1cc20-167">在搜尋準則中，選取 [**註冊機構池**]，選取 [**等於**]，選取 [**目前池 FQDN**]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="1cc20-168">在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1cc20-169">當篩選套用至現有的一組使用者時，會在篩選的使用者子集的內容（而非**所有**可能的使用者）中，選擇 [**將所有使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="1cc20-170">在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。</span><span class="sxs-lookup"><span data-stu-id="1cc20-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="1cc20-171">在 [**目的地註冊機構] 池中**，選取您要移動使用者的池。</span><span class="sxs-lookup"><span data-stu-id="1cc20-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="1cc20-172">可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cc20-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="1cc20-173">如果您選取 [**強制**]，使用者帳戶就會移動，但任何相關聯的使用者資料都會被刪除（例如，使用者已排程和連絡人的會議）。</span><span class="sxs-lookup"><span data-stu-id="1cc20-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="1cc20-174">如果您不選取它，就會移動帳戶和相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="1cc20-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="1cc20-175">使用 Windows Powershell Cmdlet 將使用者從一個池中移至另一個池</span><span class="sxs-lookup"><span data-stu-id="1cc20-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="1cc20-176">視您執行的是 Windows PowerShell 命令（本機或遠端）而定，您需要以正確的商務用 Skype Server 系統管理角色的成員身分登入，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1cc20-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="1cc20-177">是.</span><span class="sxs-lookup"><span data-stu-id="1cc20-177">a.</span></span> <span data-ttu-id="1cc20-178">如果您是在本機電腦上執行命令（例如，直接登入前端伺服器）：登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者許可權來安裝，如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="1cc20-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="1cc20-179">乙.</span><span class="sxs-lookup"><span data-stu-id="1cc20-179">b.</span></span> <span data-ttu-id="1cc20-180">如果您是在另一部電腦遠端執行命令（例如，登入您的電腦，並在標準版前端伺服器上遠端執行命令）：從指派給 CsUserAdministrator 角色或 CsAdministrator 的使用者帳戶。角色，請登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1cc20-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1cc20-181">啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1cc20-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1cc20-182">若要移動單一使用者，請使用 Move-csuser Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1cc20-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="1cc20-183">使用者要移動的使用者是 Pilar 方，而使用者會從目前指派的主池中移至 [資源庫] pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1cc20-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="1cc20-184">若要移動大量的使用者，請使用**move-csuser** Cmdlet 的篩選器，並將產生的使用者組傳遞到**move-csuser**：</span><span class="sxs-lookup"><span data-stu-id="1cc20-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="1cc20-185">**Move-csuser**和**move-csuser**的合併命令可能會造成下列情況：</span><span class="sxs-lookup"><span data-stu-id="1cc20-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


