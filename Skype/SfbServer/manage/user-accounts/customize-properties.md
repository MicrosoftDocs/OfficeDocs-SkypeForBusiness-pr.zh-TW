---
title: 自訂商務用 Skype Server 的使用者帳戶屬性
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
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本節中的程式來修改個別的使用者帳戶屬性。
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826263"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="4f836-103">自訂商務用 Skype Server 的使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="4f836-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="4f836-104">您可以使用本節中的程式來修改個別的使用者帳戶屬性。</span><span class="sxs-lookup"><span data-stu-id="4f836-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="4f836-105">在個別使用者層級上，有兩種基本作業可以進行：</span><span class="sxs-lookup"><span data-stu-id="4f836-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="4f836-106">設定特定使用者帳戶的電話語音選項</span><span class="sxs-lookup"><span data-stu-id="4f836-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="4f836-107">將使用者移至另一個集區</span><span class="sxs-lookup"><span data-stu-id="4f836-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="4f836-108">設定特定使用者帳戶的電話語音選項</span><span class="sxs-lookup"><span data-stu-id="4f836-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="4f836-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="4f836-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="4f836-110">只要個別使用者已啟用商務用 Skype Server，且該組織支援電話語音) ，您就可以自訂特定使用者 (的電話語音設定。</span><span class="sxs-lookup"><span data-stu-id="4f836-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="4f836-111">商務用 Skype Server 使用者電話語音選項包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="4f836-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="4f836-112">**已停用音訊/視頻** 使用者無法使用音訊和影片進行通話。</span><span class="sxs-lookup"><span data-stu-id="4f836-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="4f836-113">**僅限電腦對電腦** 使用者只能進行電腦對電腦音訊或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="4f836-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="4f836-114">**Enterprise Voice** 使用者可以使用商務用 Skype 伺服器基礎結構路由傳送所有來電和撥出電話。</span><span class="sxs-lookup"><span data-stu-id="4f836-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="4f836-115">使用者也可以進行電腦對電腦呼叫。</span><span class="sxs-lookup"><span data-stu-id="4f836-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="4f836-116">**遠端呼叫控制** 使用者可以使用商務用 Skype 伺服器來控制桌面電話，也可以撥打 PC 對電腦通話。</span><span class="sxs-lookup"><span data-stu-id="4f836-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="4f836-117">如需設定組織之電話語音的詳細資訊，請參閱部署檔中的 [Enable Enterprise voice in](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) 商務用 skype Server 和 [Deploy enterprise voice](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 。</span><span class="sxs-lookup"><span data-stu-id="4f836-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="4f836-118">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4f836-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f836-119">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4f836-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4f836-120">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f836-121">在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4f836-122">在表格中，按一下您要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4f836-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="4f836-123">在 **[編輯]** 功能表中，按一下 **[修改]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="4f836-124">在 **[電話語音]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4f836-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="4f836-125">若要停用使用者的音訊和視訊電話，請按一下 **[音訊/視訊已停用]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="4f836-p102">若要啟用使用者的電腦對電腦音訊通訊，但不啟用遠端呼叫控制或 Enterprise Voice，請按一下 **[僅限電腦對電腦]**。針對使用者用於電腦對電腦音訊通訊的電話，指定 **[線路 URI]** 值。</span><span class="sxs-lookup"><span data-stu-id="4f836-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="4f836-128">若要依照服務原則類別（包括 PC 對電腦音訊通訊）使用商務用 Skype 基礎結構來路由傳送使用者的電話，請按一下 [ **Enterprise Voice**]。</span><span class="sxs-lookup"><span data-stu-id="4f836-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="4f836-129">在 **[線路 URI]** 中，指定 Enterprise Voice 的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4f836-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="4f836-130">在 **[撥號對應表原則]** 和 **[語音原則]** 中，指定使用者的適當原則。</span><span class="sxs-lookup"><span data-stu-id="4f836-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="4f836-131">若要指定將使用者撥打的電話號碼轉譯為 E.164 格式時的正規化規則，請在 **[位置原則]** 中選取適當的位置設定檔。</span><span class="sxs-lookup"><span data-stu-id="4f836-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="4f836-132">若要啟用遠端呼叫控制，可讓使用者從商務用 Skype 伺服器控制其桌面電話線，以進行 PC 對電腦通話和 PC 對電話的呼叫，請按一下 [ **遠端呼叫控制**]。</span><span class="sxs-lookup"><span data-stu-id="4f836-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="4f836-133">在 **[線路 URI]** 中，指定遠端呼叫控制的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4f836-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="4f836-134">使用者必須有桌上電話和用於電話路由的專用交換機 (PBX) 連線。</span><span class="sxs-lookup"><span data-stu-id="4f836-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="4f836-135">將使用者移至另一個集區</span><span class="sxs-lookup"><span data-stu-id="4f836-135">Move users to another pool</span></span>
<span data-ttu-id="4f836-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="4f836-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="4f836-137">您可以使用商務用 Skype Server 控制台，將使用者指派至特定的伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="4f836-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="4f836-138">將所有現有使用者從執行 Lync Server 2010 或更早版本的來源集區移至複雜的 Active Directory 環境中的商務用 Skype Server 目的地集區，可能會導致 Active Directory 複寫速度變慢。</span><span class="sxs-lookup"><span data-stu-id="4f836-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="4f836-139">若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或更早版本的集區中移動使用者，也可以使用商務用 Skype Server 管理命令介面，移動使用者與 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f836-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="4f836-140">此外，篩選功能可搭配商務用 Skype Server 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="4f836-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="4f836-141">將選取的使用者移至不同的伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="4f836-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="4f836-142">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4f836-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f836-143">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4f836-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4f836-144">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f836-145">在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="4f836-146">在表格中，選取清單中的特定使用者或使用者。</span><span class="sxs-lookup"><span data-stu-id="4f836-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="4f836-147">在 [ **動作** ] 功能表上，按一下 [ **將選取的使用者移至集** 區]。</span><span class="sxs-lookup"><span data-stu-id="4f836-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="4f836-148">在 [ **移動使用者**] 中，選取要將使用者移至 [ **目的地註冊區集** 區] 的集區。</span><span class="sxs-lookup"><span data-stu-id="4f836-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="4f836-149"> (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f836-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4f836-150">如果您選取 [ **強制**]，使用者帳戶會移動，但是會刪除任何關聯的使用者資料 (例如，使用者已排程) 的會議）。</span><span class="sxs-lookup"><span data-stu-id="4f836-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="4f836-151">如果您未選取它，帳戶和相關聯的資料都會移動。</span><span class="sxs-lookup"><span data-stu-id="4f836-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="4f836-152">將一個伺服器或集區中的所有使用者移至不同的伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="4f836-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="4f836-153">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4f836-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f836-154">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4f836-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4f836-155">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f836-156">在 [ **動作** ] 功能表上，按一下 [ **將所有使用者移至集** 區]。</span><span class="sxs-lookup"><span data-stu-id="4f836-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="4f836-157">在 [ **移動使用者**] 的 [ **來源註冊集** 區] 中，選取包含您要移動之使用者帳戶的集區。</span><span class="sxs-lookup"><span data-stu-id="4f836-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="4f836-158">在 [ **目的地登記集** 區] 中，選取要將使用者移至其中的集區。</span><span class="sxs-lookup"><span data-stu-id="4f836-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="4f836-159"> (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f836-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4f836-160">如果您選取 [ **強制**]，使用者帳戶會移動，但是會刪除任何關聯的使用者資料 (例如，使用者已排程) 的會議）。</span><span class="sxs-lookup"><span data-stu-id="4f836-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="4f836-161">如果您未選取它，帳戶和相關聯的資料都會移動。</span><span class="sxs-lookup"><span data-stu-id="4f836-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="4f836-162">若要使用篩選將使用者從一個集區移至另一個集區</span><span class="sxs-lookup"><span data-stu-id="4f836-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="4f836-163">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4f836-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f836-164">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4f836-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4f836-165">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="4f836-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f836-166">在 [ **使用者搜尋**] 中，按一下 [ **搜尋**]，然後按一下 [ **新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="4f836-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="4f836-167">在搜尋準則中，選取 [ **註冊集** 區]，選取 [ **等於**]，選取 [目前的 **集區 FQDN**]，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="4f836-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="4f836-168">在 [ **動作** ] 功能表上，按一下 [ **將所有使用者移至集** 區]。</span><span class="sxs-lookup"><span data-stu-id="4f836-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f836-169">將篩選套用至現有的一組使用者時，選項 [ **將所有使用者移至** 集區] 是在篩選的使用者子集的內容中，而不是 **所有** 可能的使用者。</span><span class="sxs-lookup"><span data-stu-id="4f836-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="4f836-170">在 [ **移動使用者**] 的 [ **來源註冊集** 區] 中，選取包含您要移動之使用者帳戶的集區。</span><span class="sxs-lookup"><span data-stu-id="4f836-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="4f836-171">在 [ **目的地登記集** 區] 中，選取要將使用者移至其中的集區。</span><span class="sxs-lookup"><span data-stu-id="4f836-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="4f836-172"> (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f836-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4f836-173">如果您選取 [ **強制**]，使用者帳戶會移動，但是會刪除任何關聯的使用者資料 (例如，使用者已排程的會議，以及) 的連絡人。</span><span class="sxs-lookup"><span data-stu-id="4f836-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="4f836-174">如果您未選取它，帳戶和相關聯的資料都會移動。</span><span class="sxs-lookup"><span data-stu-id="4f836-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="4f836-175">使用 Windows Powershell Cmdlet 將使用者從一個集區移至另一個集區</span><span class="sxs-lookup"><span data-stu-id="4f836-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="4f836-176">根據您執行 Windows PowerShell 命令的方式 (（本機或遠端) ），您必須以正確商務用 Skype Server 系統管理角色的成員身分登入，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4f836-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="4f836-177">a.</span><span class="sxs-lookup"><span data-stu-id="4f836-177">a.</span></span> <span data-ttu-id="4f836-178">如果您是在本機電腦上執行命令 (例如，您可以直接登入前端伺服器) ：以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦（如 **委派安裝許可權** 中所述）。</span><span class="sxs-lookup"><span data-stu-id="4f836-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="4f836-179">b.</span><span class="sxs-lookup"><span data-stu-id="4f836-179">b.</span></span> <span data-ttu-id="4f836-180">如果您是在另一部電腦上遠端執行命令 (例如，登入您的電腦，然後從遠端的 Standard Edition 前端伺服器上執行命令) ：從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4f836-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f836-181">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="4f836-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4f836-182">若要移動單一使用者，請使用 Move-CsUser Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4f836-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="4f836-183">若要移動的使用者為使用者 Pilar Ackerman，使用者將從目前指派的主集區移至集區 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4f836-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="4f836-184">若要移動大量的使用者，請搭配 **Get-CsUser** Cmdlet 使用篩選器，並將產生的使用者集合傳遞給 **Move-CsUser**：</span><span class="sxs-lookup"><span data-stu-id="4f836-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="4f836-185">**Get-CsUser** 和 **Move-CsUser** 的合併命令可能會造成下列情況：</span><span class="sxs-lookup"><span data-stu-id="4f836-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


