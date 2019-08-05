---
title: 使用商務用 Skype Server 2015 應力與效能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 若要執行商務用 Skype Server 2015 的壓力與效能工具, 您必須能夠同時管理使用者、連絡人和使用者設定檔、設定要執行的工具, 然後查看工具產生的輸出或結果。
ms.openlocfilehash: e0cf241417272cfa16b3e332e7bafe7a112af38b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187951"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="23152-103">使用商務用 Skype Server 2015 應力與效能工具</span><span class="sxs-lookup"><span data-stu-id="23152-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="23152-104">若要執行商務用 Skype Server 2015 的壓力與效能工具, 您必須能夠同時管理使用者、連絡人和使用者設定檔、設定要執行的工具, 然後查看工具產生的輸出或結果。</span><span class="sxs-lookup"><span data-stu-id="23152-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="23152-105">執行商務用 Skype Server 2015 的壓力與效能工具有四個區域 (可執行檔為 LyncPerfTool):</span><span class="sxs-lookup"><span data-stu-id="23152-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="23152-106">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="23152-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="23152-107">設定使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="23152-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="23152-108">執行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="23152-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="23152-109">解釋結果</span><span class="sxs-lookup"><span data-stu-id="23152-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="23152-110">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="23152-110">Create Users and Contacts</span></span>
<span data-ttu-id="23152-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="23152-111"></span></span>

<span data-ttu-id="23152-112">您必須使用商務用 Skype Server 2015 (SB 2015) 使用者預配工具 (UserProvisioningTool), 為您的壓力與效能測試建立使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="23152-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="23152-113">當您閱讀主題時, 以下是有用字詞的清單:</span><span class="sxs-lookup"><span data-stu-id="23152-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="23152-114">**組織單位**-Active Directory 網域服務 (AD DS) 組織單位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="23152-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="23152-115">同盟 **/跨區池**-可與使用者從其他立即訊息 (IM) 服務進行通訊的使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="23152-116">**通訊群組清單**(或 dl)。</span><span class="sxs-lookup"><span data-stu-id="23152-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="23152-117">這些是 AD DS 中包含 AD DS 使用者清單的物件。</span><span class="sxs-lookup"><span data-stu-id="23152-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="23152-118">它們是協助跨多個使用者群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="23152-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="23152-119">[**位置資訊服務**]-商務用 Skype Server 2015 服務啟用並設定為 [每電話], 可讓您檢索增強 911 (E911) 服務的物理位置。</span><span class="sxs-lookup"><span data-stu-id="23152-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="23152-120">**美國電話號碼**-指派給使用者的電話號碼, 以及在反向編號查閱 (RNL) 中用來路由輸入和撥出電話的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="23152-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="23152-121">使用 UserProvisioningTool 建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="23152-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="23152-122">在您開始之前, 請務必確認您是以網域管理員安全性群組成員的身分登入, 以執行此工具。</span><span class="sxs-lookup"><span data-stu-id="23152-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="23152-123">您必須執行此動作, 因為您要建立 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="23152-124">您必須使用商務用 Skype Server 使用者預配工具來建立負載模擬的使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="23152-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="23152-125">商務用 skype **Server 使用者置備工具**已安裝在商務用**skype Server 壓力和效能工具**套件中。</span><span class="sxs-lookup"><span data-stu-id="23152-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="23152-126">請確定已在前端伺服器或您想要測試的標準版伺服器上執行套件安裝程式 (CapacityPlanningTool)。</span><span class="sxs-lookup"><span data-stu-id="23152-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="23152-127">您可以在前端伺服器或標準版伺服器上執行檔案 UserProvisioningTool (位於% InstalledDirectory% LyncStressAndPerfTool \ LyncStress), 以啟動商務用 Skype Server 使用者預配工具。</span><span class="sxs-lookup"><span data-stu-id="23152-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="23152-128">當您建立大量的使用者 (例如, 10000 或更多) 時, 請執行 UserProvisioningTool。</span><span class="sxs-lookup"><span data-stu-id="23152-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="23152-129">您必須執行此動作, 因為工具將會建立並設定*新*的 AD 使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="23152-130">當使用者提供工具開啟時, 請按一下 [設定], 然後選取載入設定。</span><span class="sxs-lookup"><span data-stu-id="23152-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="23152-131">若要開始設定使用者和連絡人, 請載入套件中包含的預設檔案, 名為「SampleData」。</span><span class="sxs-lookup"><span data-stu-id="23152-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="23152-132">這將會使用範例資料來預填欄位, 以便將它與您的部署相關。</span><span class="sxs-lookup"><span data-stu-id="23152-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="23152-133">如果您有預先配置的 XML 檔案, 而該檔案已包含您的自訂設定, 您可以改為載入該檔案。</span><span class="sxs-lookup"><span data-stu-id="23152-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="23152-134">如以下各節所述, 請在 [使用者預配工具] 中填入欄位。</span><span class="sxs-lookup"><span data-stu-id="23152-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="23152-135">若要設定伺服器選項:</span><span class="sxs-lookup"><span data-stu-id="23152-135">To configure server options:</span></span>

1. <span data-ttu-id="23152-136">在 [**前端池 FQDN** ] 欄位中, 輸入標準版伺服器的完整功能變數名稱 (FQDN), 或是您要主持使用者的前端池。</span><span class="sxs-lookup"><span data-stu-id="23152-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="23152-137">在 [**使用者名稱首碼**] 欄位中, 輸入您要用來 bust 您的使用者名稱以進行測試的前置詞 (例如 "TestUser")。</span><span class="sxs-lookup"><span data-stu-id="23152-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="23152-138">在 [**密碼**] 欄位中, 輸入將在所有測試使用者帳戶中使用的密碼。</span><span class="sxs-lookup"><span data-stu-id="23152-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="23152-139">在 [ **Account Domain] (帳戶網域**) 欄位中, 輸入您目前的 AD 網域 (您要在其中建立測試使用者) 的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="23152-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="23152-140">在 [**組織單位**] 欄位中, 輸入您要建立這些測試使用者之 AD 網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="23152-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="23152-141">(如果 OU 尚不存在, 就會為您建立)。</span><span class="sxs-lookup"><span data-stu-id="23152-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="23152-142">在 [**電話區功能變數代碼**] 欄位中, 輸入要在所有測試使用者帳戶中使用的三位數區功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="23152-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="23152-143">請確認您所選的區號與 AD 中其他使用者的區功能變數代碼不會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="23152-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="23152-144">如果您想要啟用企業語音測試使用者, 請按一下以選取 [**已啟用語音**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="23152-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="23152-145">在 [**使用者數目**] 欄位中, 給出您想要建立的測試使用者總數。</span><span class="sxs-lookup"><span data-stu-id="23152-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="23152-146">在 [**起始索引**] 欄位中, 提供要用來做為使用者名稱首碼尾碼的起始數位 (例如, 首碼是 "TestUser", 而第一個名稱在下列範例中將結束于 "0"。)</span><span class="sxs-lookup"><span data-stu-id="23152-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![[使用者供給] 工具顯示 [使用者建立] 索引標籤。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="23152-148">[建立使用者] 按鈕</span><span class="sxs-lookup"><span data-stu-id="23152-148">Create Users button</span></span>

<span data-ttu-id="23152-149">當您按一下 [**建立使用者**] 按鈕時, 您輸入的輸入參數就會得到驗證。</span><span class="sxs-lookup"><span data-stu-id="23152-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="23152-150">如果有任何驗證錯誤, 系統會提示您修正錯誤。</span><span class="sxs-lookup"><span data-stu-id="23152-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="23152-151">或者, 如果所有值都正確無誤, 使用者就會開始出現在 AD 中 (在您指定的任何 OU 中)。</span><span class="sxs-lookup"><span data-stu-id="23152-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="23152-152">在工具執行時, 您會看到一個進度列。</span><span class="sxs-lookup"><span data-stu-id="23152-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="23152-153">在進度列生效時不要關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="23152-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="23152-154">使用者建立需要時間, 因此請據此規劃。</span><span class="sxs-lookup"><span data-stu-id="23152-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="23152-155">這個程式可能需要幾分鐘的時間才能讓幾個使用者使用, 幾個小時就能完成許多使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="23152-156">如果您在測試環境中沒有 AD 網網域控制站的存取權, 您仍然可以在您指定要建立的使用者範圍中以其中一個使用者的身分登入, 以驗證使用者建立。</span><span class="sxs-lookup"><span data-stu-id="23152-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="23152-157">請記得使用首碼及尾碼, 以及 @sipDomain 作為使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="23152-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="23152-158">以下是範例: <em>TestUser20@contoso.net</em> 。</span><span class="sxs-lookup"><span data-stu-id="23152-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="23152-159">如果使用者已經存在, 按一下 [建立使用者] 按鈕就會以任何設定變更進行更新。</span><span class="sxs-lookup"><span data-stu-id="23152-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="23152-160">[刪除使用者] 按鈕</span><span class="sxs-lookup"><span data-stu-id="23152-160">Delete Users button</span></span>

<span data-ttu-id="23152-161">當您按一下 [**刪除使用者**] 按鈕時, 會驗證索引標籤的輸入參數。</span><span class="sxs-lookup"><span data-stu-id="23152-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="23152-162">如果有驗證錯誤, 系統會提示您修正這些錯誤, 如果輸入值正確, 指定的測試使用者將會停用, 並從 Active Directory 中刪除。</span><span class="sxs-lookup"><span data-stu-id="23152-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="23152-163">同樣地, 進度列會出現在此索引標籤的底部, 而且您不應該在進度列開啟時關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="23152-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23152-164">僅支援美國格式的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="23152-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="23152-165">電話號碼永遠會指派給使用者, 而由 UserProvisioningTool 所建立的所有使用者預設都會啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="23152-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="23152-166">使用電話號碼 (例如會議自動語音應答或 UC PSTN 通話) 的任何案例, 都可以使用此電話號碼來正確路由通話。</span><span class="sxs-lookup"><span data-stu-id="23152-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="23152-167">基於這個原因,*每個使用者*都必須有*唯一的電話號碼*。</span><span class="sxs-lookup"><span data-stu-id="23152-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="23152-168">**如果您必須建立使用者兩次, 除非您使用不同的區號, 或使用 Disable Move-csuser Cmdlet 來停用先前的使用者, 否則命令將會失敗。**</span><span class="sxs-lookup"><span data-stu-id="23152-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="23152-169">在您建立連絡人之前, 您必須先完成使用者複製 (從 [使用者] 索引標籤完成)。</span><span class="sxs-lookup"><span data-stu-id="23152-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="23152-170">如果您剛剛建立使用者, 您必須等到商務用 Skype Server 複製完成, 然後填入資料庫中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="23152-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="23152-171">**如果使用者還沒有完成複製, 您會看到錯誤。**</span><span class="sxs-lookup"><span data-stu-id="23152-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="23152-172">如果商務用 Skype Server 2015 前端服務已啟動, 或是成功在您指定之總數的最後一個使用者上執行 Move-csuser Cmdlet, 您就會知道使用者已完成複製的時間。</span><span class="sxs-lookup"><span data-stu-id="23152-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="23152-173">連絡人 [建立] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-173">Contacts Creation tab</span></span>

<span data-ttu-id="23152-174">這個索引標籤可讓您為您的測試提供使用者的連絡人詳細資料。</span><span class="sxs-lookup"><span data-stu-id="23152-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![[使用者供給] 工具顯示 [內容建立] 索引標籤。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="23152-176">若要設定使用者的連絡人, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="23152-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="23152-177">在 [**每位使用者的平均聯絡**人] 欄位中, 輸入要在連絡人清單中為每位使用者填入的連絡人的平均數目。</span><span class="sxs-lookup"><span data-stu-id="23152-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="23152-178">如果您想要為每位使用者建立同等數量的連絡人, 請選取 [**固定**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="23152-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="23152-179">如果您想要變更為使用者建立的連絡人數目, 請清除該核取方塊。</span><span class="sxs-lookup"><span data-stu-id="23152-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="23152-180">在 [**每位使用者的平均連絡人群組**] 欄位中, 輸入每位使用者的連絡人群組數量。</span><span class="sxs-lookup"><span data-stu-id="23152-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="23152-181">這個數位必須小於**每位使用者的平均聯絡**人。</span><span class="sxs-lookup"><span data-stu-id="23152-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="23152-182">在 [**聯盟/跨系池連絡人百分比**] 欄位中, 為0到100之間的數位。</span><span class="sxs-lookup"><span data-stu-id="23152-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="23152-183">系統會使用聯盟使用者建立此連絡人的百分比。</span><span class="sxs-lookup"><span data-stu-id="23152-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="23152-184">在 [同盟 **/交叉池使用者**編號] 欄位中, 為將新增至本機使用者連絡人清單的聯盟使用者提供使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="23152-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="23152-185">在 [同盟 **/跨池使用者 SIP 網域**] 欄位中, 請提供聯盟使用者的 SIP 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="23152-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="23152-186">在 [**使用者建立**] 索引標籤中, 請確定資訊正確無誤。</span><span class="sxs-lookup"><span data-stu-id="23152-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="23152-187">您的連絡人將會從 [使用者建立] 索引標籤上的值建立。</span><span class="sxs-lookup"><span data-stu-id="23152-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="23152-188">按一下 [**建立連絡人**], 開始建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="23152-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="23152-189">這個程式可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="23152-189">This process can take several minutes.</span></span> <span data-ttu-id="23152-190">完成之後, 會出現一個對話方塊, 其中顯示 [作業已順利完成] 訊息。</span><span class="sxs-lookup"><span data-stu-id="23152-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="23152-191">您可以從以使用者 [建立] 索引標籤建立的使用者身分登入, 以驗證所建立的連絡人。</span><span class="sxs-lookup"><span data-stu-id="23152-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
> [!NOTE]
> <span data-ttu-id="23152-192">建立連絡人之後, 此工具會重新開機目標池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="23152-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="23152-193">前端伺服器可能需要較長時間 (最多2小時) 才能啟動, 視這個作業建立的連絡人數量而定。</span><span class="sxs-lookup"><span data-stu-id="23152-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="23152-194">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="23152-194">Distribution List</span></span>

<span data-ttu-id="23152-195">商務用 Skype Server 2015 的應力與效能工具可以模擬商務用 Skype 2015 用戶端中的通訊群組清單 (DL) 擴充功能。</span><span class="sxs-lookup"><span data-stu-id="23152-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="23152-196">如果您不想在使用者供給工具中啟用 DL 延伸, 您可以略過這個步驟。</span><span class="sxs-lookup"><span data-stu-id="23152-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![[使用者供給] 工具顯示 [通訊群組清單建立] 索引標籤。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="23152-198">[通訊群組清單] 索引標籤可讓您建立使用壓力與效能工具來進行通訊群組清單擴充功能的 Dl。</span><span class="sxs-lookup"><span data-stu-id="23152-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="23152-199">建立 DLs 之前, 必須先部署商務用 Skype Server 2015, 包括擁有 run ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="23152-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="23152-200">如果這項操作沒有完成, 則在 AD 架構中不會存在 DL 屬性, 因此該工具將無法建立 DLs。</span><span class="sxs-lookup"><span data-stu-id="23152-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="23152-201">若要設定通訊群組清單:</span><span class="sxs-lookup"><span data-stu-id="23152-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="23152-202">在 [**通訊群組清單數目**] 欄位中, 為您想要建立的 dl 加總數量 (此處的建議是, 您的值是您所擁有的使用者數加倍)。</span><span class="sxs-lookup"><span data-stu-id="23152-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="23152-203">在 [**通訊群組清單首碼**] 欄位中, 輸入您所建立的所有 DLs 將擁有的首碼, 例如*testDL* 。</span><span class="sxs-lookup"><span data-stu-id="23152-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="23152-204">也就是說, 在 100 Dl, 您的 DL 名稱看起來會像這樣: testDL0、testDL1、最多 testDL99。</span><span class="sxs-lookup"><span data-stu-id="23152-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="23152-205">在 [ **Dist] 中的 [最小成員] 清單**中, 輸入要放在每個 DL 中的最小使用者數。</span><span class="sxs-lookup"><span data-stu-id="23152-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="23152-206">在 [ **Dist] 中的 [最大成員**數] 欄位中, 輸入要在每個 DL 中新增的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="23152-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="23152-207">建立通訊群組清單按鈕</span><span class="sxs-lookup"><span data-stu-id="23152-207">Create Distribution Lists button</span></span>

<span data-ttu-id="23152-208">當您按一下 [建立通訊群組清單] 按鈕時, 該工具會查詢 Active Directory, 以查看是否有符合該首碼與編號的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="23152-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="23152-209">此工具會建立任何不存在的 Dl。</span><span class="sxs-lookup"><span data-stu-id="23152-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="23152-210">將成員新增到這些新建立的通訊群組清單時, 會從 [使用者建立] 索引標籤上指定的範圍中選擇使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="23152-211">位置資訊服務 [配置] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-211">Location Info Service Config tab</span></span>

<span data-ttu-id="23152-212">商務用 Skype Server 2015 的應力與效能工具也可以產生位置資訊服務的虛擬設定檔。</span><span class="sxs-lookup"><span data-stu-id="23152-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="23152-213">請注意, 位置資訊服務通常不會對伺服器產生顯著的效能影響。</span><span class="sxs-lookup"><span data-stu-id="23152-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![顯示位置資訊服務 [配置] 索引標籤的使用者供給工具。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="23152-215">如果您選擇測試此功能, 請填寫表單中的值, 然後按一下將會建立的 [產生 .LIS 配置檔案] 按鈕。名為的 CSV 檔案:</span><span class="sxs-lookup"><span data-stu-id="23152-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="23152-216">LIS_Subnet</span><span class="sxs-lookup"><span data-stu-id="23152-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="23152-217">LIS_Switches</span><span class="sxs-lookup"><span data-stu-id="23152-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="23152-218">LIS_Ports</span><span class="sxs-lookup"><span data-stu-id="23152-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="23152-219">LIS_WAP</span><span class="sxs-lookup"><span data-stu-id="23152-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="23152-220">若要將這些檔案匯入 IIS 資料庫, 請使用下列 PowerShell Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="23152-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="23152-221">Set-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="23152-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="23152-222">Set-CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="23152-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="23152-223">Set-CsLisPort</span><span class="sxs-lookup"><span data-stu-id="23152-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="23152-224">Set-CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="23152-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="23152-225">設定使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="23152-225">Configure User Profile</span></span>
<span data-ttu-id="23152-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="23152-226"></span></span>

<span data-ttu-id="23152-227">建立使用者之後 (透過使用者建立工具), 您可以使用商務用 Skype Server 2015 載入組態工具 (UserProfileGenerator) 來設定使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="23152-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="23152-228">執行商務用 Skype Server 2015 載入組態工具</span><span class="sxs-lookup"><span data-stu-id="23152-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="23152-229">啟動 [載入設定] 工具 (UserProfileGenerator) 並填入索引標籤。</span><span class="sxs-lookup"><span data-stu-id="23152-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="23152-230">這個工具會為您需要執行模擬的每個用戶端電腦建立目錄。</span><span class="sxs-lookup"><span data-stu-id="23152-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="23152-231">每個用戶端目錄都隨附一個腳本來啟動商務用 Skype Server 2015 應力和效能工具 (LyncPerfTool)。</span><span class="sxs-lookup"><span data-stu-id="23152-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="23152-232">下列各節將提供範例, 說明如何在商務用 Skype Server 2015 載入設定工具的每個索引標籤上填入欄位。</span><span class="sxs-lookup"><span data-stu-id="23152-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="23152-233">載入組態工具 (UserProfileGenerator) 中使用的使用者特定值, 必須符合在該池的商務用 Skype Server 2015 使用者建立工具 (UserProvisioningTool) 中指定的值。</span><span class="sxs-lookup"><span data-stu-id="23152-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="23152-234">[常用設定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-234">Common Configuration tab</span></span>

<span data-ttu-id="23152-235">[載入設定] 工具的 [**一般**設定] 索引標籤如下所示。</span><span class="sxs-lookup"><span data-stu-id="23152-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="23152-236">填寫 [通用設定] 索引標籤的欄位, 如以下步驟所述。</span><span class="sxs-lookup"><span data-stu-id="23152-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![[使用者供給] 索引標籤顯示 [一般設定] 索引標籤。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="23152-238">在 [**可用的電腦數目**] 欄位中, 輸入您要用來執行壓力與效能工具 (LyncPerfTool) 的電腦數目。</span><span class="sxs-lookup"><span data-stu-id="23152-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="23152-239">我們建議您針對您要模擬的每個4500使用者使用一部電腦, 但如果您減少載入層級, 或只使用工具的可用功能子集 (在 [一般情況] 索引標籤上設定載入層級), 則該數位可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="23152-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="23152-240">在 [**使用者名稱的首碼**] 欄位中, 輸入所有使用者之 [使用者名稱] 欄位的首碼。</span><span class="sxs-lookup"><span data-stu-id="23152-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="23152-241">若要登入 [統一資源識別項 (URI)], 請: *UserPrefix [使用者起始索引 ...](使用者數目-1)]@User 網域*, 例如 myUser009@Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="23152-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="23152-242">在 [**所有使用者的密碼**] 欄位中, 輸入使用者建立時所用的密碼。</span><span class="sxs-lookup"><span data-stu-id="23152-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="23152-243">如果您將此欄位保留空白, 則會將該使用者名稱設定為密碼。</span><span class="sxs-lookup"><span data-stu-id="23152-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="23152-244">在 [**使用者起始索引**] 欄位中, 輸入要設定的第一個使用者索引。</span><span class="sxs-lookup"><span data-stu-id="23152-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="23152-245">您可以針對不同的負載類型或等級設定不同的範圍, 但您必須針對您想要設定的範圍執行一次 [載入設定] 工具 (UserProfileGenerator)。</span><span class="sxs-lookup"><span data-stu-id="23152-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="23152-246">在 [**使用者數目**] 欄位中, 輸入您要設定的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="23152-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="23152-247">在 [**使用者網域**] 欄位中, 輸入用於 SIP URI 的網域。</span><span class="sxs-lookup"><span data-stu-id="23152-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="23152-248">這是用來構造每個使用者的 SIP URI, 以登入商務用 Skype Server 2015 前端伺服器或標準版伺服器, 而且可能與帳戶網域不同。</span><span class="sxs-lookup"><span data-stu-id="23152-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="23152-249">在 [ **Account Domain] (帳戶網域**) 欄位中, 輸入 AD DS 網域登入。</span><span class="sxs-lookup"><span data-stu-id="23152-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="23152-250">在 [ **MPOP 百分比**(多重目前狀態百分比)] 欄位中, 為從多個電腦或裝置登入的使用者百分比提供值, 例如 10%。</span><span class="sxs-lookup"><span data-stu-id="23152-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="23152-251">在 [**每秒登錄數 (每個實例)** ] 欄位中, 輸入並行端點的最大數目。</span><span class="sxs-lookup"><span data-stu-id="23152-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="23152-252">這是您的使用者最多登入次數, 而建議是每秒小於/等於2的速率 (<= 2)。</span><span class="sxs-lookup"><span data-stu-id="23152-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="23152-253">在 [**存取代理伺服器] 或 [池 FQDN** ] 欄位中, 輸入您要用戶端連線之伺服器的完整功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="23152-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="23152-254">如果使用者是在外部登入, 您必須輸入訪問 proxy proxy。</span><span class="sxs-lookup"><span data-stu-id="23152-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="23152-255">如果使用者是 internal, 請提供其企業版池或標準版伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="23152-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="23152-256">在 [ **Port** ] (埠) 欄位中, 輸入您希望使用者使用的 SIP 埠 (預設值為 5061)。</span><span class="sxs-lookup"><span data-stu-id="23152-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="23152-257">針對 [**外部網路伺服器設定**] 欄位, 請授與 [存取代理伺服器] 或 [池 FQDN], 然後再按一次**埠**。</span><span class="sxs-lookup"><span data-stu-id="23152-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="23152-258">這些設定僅用於外部端點的負載模擬。</span><span class="sxs-lookup"><span data-stu-id="23152-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="23152-259">[一般情況] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-259">General Scenarios tab</span></span>

![[載入設定] 工具顯示 [一般情況] 索引標籤。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="23152-261">您可以透過判斷您想要執行或保留停用的內容, 來設定每個一般案例所提供的負載等級與參數。</span><span class="sxs-lookup"><span data-stu-id="23152-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="23152-262">以下是您的一般選項:</span><span class="sxs-lookup"><span data-stu-id="23152-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="23152-263">針對所有欄位載入層級值, 但會**停用**、**低**、**中**、**高**或**自訂**的 [本機資訊服務]。</span><span class="sxs-lookup"><span data-stu-id="23152-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="23152-264">如果您選取任何設定但已停用, 則會針對每個用戶端產生配置。</span><span class="sxs-lookup"><span data-stu-id="23152-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="23152-265">[高] 會產生伺服器支援的最大負載;[中] 是高負載的 60%;低為 30%。</span><span class="sxs-lookup"><span data-stu-id="23152-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="23152-266">**立即訊息-** 這包括對等與會議;針對載入層級選擇適當的值。</span><span class="sxs-lookup"><span data-stu-id="23152-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="23152-267">**音訊會議-** 選擇*僅限*音訊會議的負載等級。</span><span class="sxs-lookup"><span data-stu-id="23152-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="23152-268">在 [**語音案例**] 區段中, 稍後會 tackled 對等通話。</span><span class="sxs-lookup"><span data-stu-id="23152-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="23152-269">開啟 [**高級**] 索引標籤以啟用 [各頁]。</span><span class="sxs-lookup"><span data-stu-id="23152-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="23152-270">**應用程式共用-** 選擇應用程式共用的負載層級。</span><span class="sxs-lookup"><span data-stu-id="23152-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="23152-271">**資料共同作業-** 選擇資料共同作業的負載層級, 包括資料會議。</span><span class="sxs-lookup"><span data-stu-id="23152-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="23152-272">**通訊群組清單延伸-** 按一下 [**高級**] 按鈕, 然後在 [使用者建立工具] (UserProvisioningTool) 的 [DL] 索引標籤上, 使用相同的值填入欄位。</span><span class="sxs-lookup"><span data-stu-id="23152-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="23152-273">選擇負載等級。</span><span class="sxs-lookup"><span data-stu-id="23152-273">Choose a load level.</span></span>
    
- <span data-ttu-id="23152-274">**通訊錄網頁查詢-** 這是通訊錄查閱服務, 而不是通訊錄檔案下載。</span><span class="sxs-lookup"><span data-stu-id="23152-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="23152-275">如果您想要針對通訊錄檔案下載啟用此選項, 請按一下 [**高級**] 按鈕, 並將 [ **EnableABSDownload** ] 設定為 True。</span><span class="sxs-lookup"><span data-stu-id="23152-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="23152-276">為載入層級提供值。</span><span class="sxs-lookup"><span data-stu-id="23152-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="23152-277">**回應群組服務-** 按一下 [**高級**] 按鈕, 然後指定您在已提供回應群組服務代理程式時所建立之回應群組的 uri。</span><span class="sxs-lookup"><span data-stu-id="23152-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="23152-278">您必須選擇至少一個回應群組。</span><span class="sxs-lookup"><span data-stu-id="23152-278">You must choose at least one response group.</span></span> <span data-ttu-id="23152-279">若要使用其他, 請以分號分隔回應群組。</span><span class="sxs-lookup"><span data-stu-id="23152-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="23152-280">將**RGSUriSuffixStartIndex**和**RGSUriSuffixEndIndex**更新為實際值。</span><span class="sxs-lookup"><span data-stu-id="23152-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="23152-281">選擇負載等級。</span><span class="sxs-lookup"><span data-stu-id="23152-281">Choose a load level.</span></span>
    
- <span data-ttu-id="23152-282">**位置資訊服務-** 選取 [已啟用] 或 [已停用] 的負載等級。</span><span class="sxs-lookup"><span data-stu-id="23152-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="23152-283">每個案例旁邊都有一個 [高級] 按鈕, 以及一組可讓您變更預設設定的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="23152-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="23152-284">選擇 [*隨機*] 會讓此工具產生一段時間內將建立的會議類比。</span><span class="sxs-lookup"><span data-stu-id="23152-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="23152-285">選擇 [*大型*會議] 表示將會模擬大型會議案例。</span><span class="sxs-lookup"><span data-stu-id="23152-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="23152-286">[*外部*] 告訴該工具也要模仿外部使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="23152-287">這些按鈕和核取方塊是每個案例專用的額外值, 會變更壓力和效能工具的行為, 並使自訂成為可能。</span><span class="sxs-lookup"><span data-stu-id="23152-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="23152-288">針對 [一般案例] 索引標籤上的每個案例 ([位置資訊服務] 除外), 如果 [載入層級] 的值是 [**自訂**], 則會使用 [高級] 對話方塊中對應的欄位來計算交談比率。</span><span class="sxs-lookup"><span data-stu-id="23152-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="23152-289">根據案例而定, 功能變數名稱可能會有所不同, 但欄位描述將會*是: 請注意, 只有從下拉式功能表中選取 [自訂] 時, 才會使用此號碼*。</span><span class="sxs-lookup"><span data-stu-id="23152-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="23152-290">[**高**]、[**中**] 和 [**低**] 值會依與所有案例平衡的使用者模型來變更每個模態的交談比率。</span><span class="sxs-lookup"><span data-stu-id="23152-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="23152-291">如果由於預期使用量差異而需要變更每個模態的負載等級, 請使用自訂交談比率。</span><span class="sxs-lookup"><span data-stu-id="23152-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="23152-292">[語音案例] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-292">Voice Scenarios tab</span></span>

<span data-ttu-id="23152-293">這是設定所有語音相關案例的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="23152-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![[載入設定工具語音案例] 索引標籤。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="23152-295">您的選項包括:</span><span class="sxs-lookup"><span data-stu-id="23152-295">Your options are:</span></span>
  
- <span data-ttu-id="23152-296">**VoIP-** 按一下 [**高級**] 按鈕, 然後新增 [PhoneAreaCode] 和 [LocationProfile] (撥號計畫) 欄位的值。</span><span class="sxs-lookup"><span data-stu-id="23152-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="23152-297">您也會為載入層級提供一個值。</span><span class="sxs-lookup"><span data-stu-id="23152-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="23152-298">如果您選擇 [VoIP] 或 [UC/PSTN 閘道] 的負載等級, 則會產生公用交換電話網絡 (PSTN) 至整合通訊 (UC) 配置檔案, 以模擬外部呼叫。</span><span class="sxs-lookup"><span data-stu-id="23152-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="23152-299">**UC/PSTN 閘道-** 您必須選擇負載等級值, 當您選擇 [停用] 以外的任何專案時, 您也可以按一下 [**高級**] 按鈕, 為 PSTN 區功能變數代碼提供一個值。</span><span class="sxs-lookup"><span data-stu-id="23152-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="23152-300">按一下 [中繼伺服器] 和 [PSTN] 底下的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="23152-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="23152-301">請確定您已為區號設定路由。</span><span class="sxs-lookup"><span data-stu-id="23152-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="23152-302">您可以使用商務用 Skype 的 [控制台] 或 [商務用 Skype] 管理命令介面來驗證您的語音路線設定。</span><span class="sxs-lookup"><span data-stu-id="23152-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="23152-303">**會議助理-** 為載入層級提供一個值。</span><span class="sxs-lookup"><span data-stu-id="23152-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="23152-304">[停用] 以外的任何值都會啟用 [**電話號碼**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="23152-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="23152-305">輸入您要使用之自動助手的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="23152-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="23152-306">按一下 [**高級**], 然後為 [ **LocationProfile** ] 欄位提供一個值。</span><span class="sxs-lookup"><span data-stu-id="23152-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="23152-307">**呼叫停用服務-** 在這裡, 提供一個負載等級。</span><span class="sxs-lookup"><span data-stu-id="23152-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="23152-308">**中繼伺服器與 PSTN-** 每個您想要使用的中繼伺服器都需要自己的 PSTN 模擬器。</span><span class="sxs-lookup"><span data-stu-id="23152-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="23152-309">在您決定要將哪些用戶端用於模擬器之後, 請設定您的中繼伺服器將呼叫路由到您所設定的 PSTN 模擬器上的該電腦。</span><span class="sxs-lookup"><span data-stu-id="23152-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="23152-310">按一下 [ **Add** ] (新增) 按鈕, 為中繼伺服器設定值。</span><span class="sxs-lookup"><span data-stu-id="23152-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="23152-311">每個案例旁邊都有一個 [高級] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="23152-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="23152-312">[高級] 對話方塊包含可變更壓力與效能工具行為並啟用自訂之每個案例的特定設定。</span><span class="sxs-lookup"><span data-stu-id="23152-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="23152-313">> 針對 [語音案例] 索引標籤上的每個案例, 如果 [載入層級] 的值是 [**自訂**], 則會使用 [高級] 對話方塊中對應的欄位來計算交談比率。</span><span class="sxs-lookup"><span data-stu-id="23152-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="23152-314">根據案例而定, 功能變數名稱可能會有所不同, 但欄位描述將會*是: 請注意, 只有從下拉式功能表中選取 [自訂] 時, 才會使用此號碼*。</span><span class="sxs-lookup"><span data-stu-id="23152-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="23152-315">[Web App] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-315">Web App tab</span></span>

![載入 [組態工具]、[Web 應用程式] 索引標籤。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="23152-317">Web App 可透過安裝在前端伺服器上的統一通訊 Web API (UCWA) 伺服器, 來支援會議案例。</span><span class="sxs-lookup"><span data-stu-id="23152-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="23152-318">使用 [Web 應用程式] 索引標籤來設定所有與 Web 應用程式相關的案例。</span><span class="sxs-lookup"><span data-stu-id="23152-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="23152-319">選項包括:</span><span class="sxs-lookup"><span data-stu-id="23152-319">Options are:</span></span>
  
- <span data-ttu-id="23152-320">**一般 Web App 設定-** 按一下 [**其他設定**] 按鈕, 並將**ReachTargetServerUrl**設定為前端池 VIP 的目錄池虛擬 IP (VIP)。</span><span class="sxs-lookup"><span data-stu-id="23152-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="23152-321">**應用程式共用-** 選取 [負載等級] 的值。</span><span class="sxs-lookup"><span data-stu-id="23152-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="23152-322">**資料共同作業-** 選取 [負載等級] 的值。</span><span class="sxs-lookup"><span data-stu-id="23152-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="23152-323">**立即訊息-** 選取 [負載等級] 的值。</span><span class="sxs-lookup"><span data-stu-id="23152-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="23152-324">**語音會議-** 選取 [負載等級] 的值。</span><span class="sxs-lookup"><span data-stu-id="23152-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="23152-325">每個案例旁邊都有一個 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="23152-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="23152-326">[高級] 對話方塊包含每個案例專用的值, 這些值會變更壓力與效能工具的行為, 並啟用自訂。針對每一個 Web 應用程式案例 >, 如果載入層級是 [**自訂**], 則是在中**指定的值。使用 ConversationsPerHour**欄位, 而不是預設值。</span><span class="sxs-lookup"><span data-stu-id="23152-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="23152-327">[行動] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-327">Mobility tab</span></span>

<span data-ttu-id="23152-328">使用此索引標籤來設定行動相關的所有案例。</span><span class="sxs-lookup"><span data-stu-id="23152-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![載入 [設定工具行動] 索引標籤。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="23152-330">這裡的選項如下:</span><span class="sxs-lookup"><span data-stu-id="23152-330">The options here are:</span></span>
  
- <span data-ttu-id="23152-331">**一般行動設定-** 按一下 [**其他設定**], 然後將 [欄位 UcwaTargetServerUrl] 設定為 [控制器池虛擬 IP (VIP)] 或 [頂層端池 VIP]。</span><span class="sxs-lookup"><span data-stu-id="23152-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="23152-332">目前**狀態與 P2P 立即訊息/音訊-** 選取 [負載等級] 的值, 即可啟用行動模擬。</span><span class="sxs-lookup"><span data-stu-id="23152-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="23152-333">每個案例旁邊都有一個 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="23152-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="23152-334">[高級] 對話方塊包含每個案例專用的值, 這些值會變更壓力與效能工具的行為, 並啟用自訂 >。針對每一個行動案例, 如果\*\*\*\* 載入層級為 [**自訂], 則為在中指定的值使用 ConversationsPerHour**欄位, 而不是預設值。</span><span class="sxs-lookup"><span data-stu-id="23152-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="23152-335">[摘要] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="23152-335">Summary tab</span></span>

<span data-ttu-id="23152-336">[摘要] 索引標籤會指出要在每個案例中使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![載入 [組態工具摘要] 索引標籤。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="23152-338">[摘要] 索引標籤會指出要在每個案例中使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="23152-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="23152-339">若要手動設定使用者編號範圍, 請選取 [**啟用自訂使用者範圍產生**] 核取方塊, 然後在包含您要自訂之使用者範圍的資料表中, 按兩下該案例。</span><span class="sxs-lookup"><span data-stu-id="23152-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="23152-340">Check **(RunClient) 在啟動時加入登入延遲**, 以便在產生的批次檔案中包含延遲, 以對應到登入速率。</span><span class="sxs-lookup"><span data-stu-id="23152-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="23152-341">在登入大量的使用者時, 這對避免伺服器超載很有用。</span><span class="sxs-lookup"><span data-stu-id="23152-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="23152-342">按一下 [**產生**檔案], 然後選取您要產生配置的資料夾。</span><span class="sxs-lookup"><span data-stu-id="23152-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="23152-343">成功建立檔案後, 就會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="23152-343">A dialog box will appear when your files have been successfully created.</span></span>
  
![[載入設定檔已成功產生] 訊息方塊。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="23152-346">執行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="23152-346">Run LyncPerfTool</span></span>
<span data-ttu-id="23152-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="23152-347"></span></span>

<span data-ttu-id="23152-348">您必須先建立使用者、連絡人和案例, 然後才能執行商務用 Skype Server 2015 應力和效能工具 (LyncPerfTool)。</span><span class="sxs-lookup"><span data-stu-id="23152-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="23152-349">如需使用工具執行這些動作的詳細資料, 請參閱[建立使用者和連絡人](using-the-tool.md#BKMK_CreateUsersAndContacts), 並在本文先前[設定使用者設定檔](using-the-tool.md#BKMK_UserProfile)。</span><span class="sxs-lookup"><span data-stu-id="23152-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="23152-350">執行這些工具時, 也會產生一個檔案, 該檔案會以壓力與效能工具一起執行, 做為包含所需參數的批次檔案的一部分。</span><span class="sxs-lookup"><span data-stu-id="23152-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="23152-351">執行商務用 Skype Server 2015 應力與效能工具</span><span class="sxs-lookup"><span data-stu-id="23152-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="23152-352">載入組態工具 (UserProfileGenerator) 會建立一個批次處理檔案, 讓您以執行壓力與效能工具 (LyncPerfTool), 方法是註冊效能計數器並載入 XML 設定檔。</span><span class="sxs-lookup"><span data-stu-id="23152-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="23152-353">批次處理檔案會針對每個設定檔執行 LyncPerfTool 的一個實例。</span><span class="sxs-lookup"><span data-stu-id="23152-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="23152-354">若要執行批次檔案, 請依照下列步驟執行:</span><span class="sxs-lookup"><span data-stu-id="23152-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="23152-355">執行壓力與效能測試</span><span class="sxs-lookup"><span data-stu-id="23152-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="23152-356">在每個用戶端電腦上都有 LyncPerfTool 的目錄中, 將資料夾與配置資料夾及檔案一起複製。</span><span class="sxs-lookup"><span data-stu-id="23152-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="23152-357">(例如, 如果您在名為 1.28 _ 13.16.16 的資料夾中產生了設定檔案, 請將該資料夾複製到其中有 LyncPerfTool .exe 的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="23152-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="23152-358">在每個用戶端執行此動作。)</span><span class="sxs-lookup"><span data-stu-id="23152-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="23152-359">流覽至用戶端資料夾, 並執行**RunClient**批次腳本。</span><span class="sxs-lookup"><span data-stu-id="23152-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="23152-360">您可以在 Windows 資源管理器中按兩下批次檔案, 該檔案將會執行該用戶端的所有設定檔。</span><span class="sxs-lookup"><span data-stu-id="23152-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="23152-361">您也可以使用下列語法, 從用戶端資料夾執行腳本:</span><span class="sxs-lookup"><span data-stu-id="23152-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="23152-362">若要直接執行壓力與效能工具, 請開啟命令提示字元, 然後在命令列中輸入下列命令 (第一次執行此動作時, 請務必註冊效能計數器`regsvr32 /i /n /s LyncPerfToolPerf.dll`, 如本主題後面的記事所示):</span><span class="sxs-lookup"><span data-stu-id="23152-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="23152-363">若要讓工具顯示配置檔案中的值, 請在前面`/displayfile`的命令中加入參數, 使其看起來像這樣:</span><span class="sxs-lookup"><span data-stu-id="23152-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="23152-364">若要*結束*處理常式, 請按 Ctrl + C。</span><span class="sxs-lookup"><span data-stu-id="23152-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23152-365">在直接執行壓力與效能工具之前, 您必須透過下列命令來註冊效能計數器:`regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="23152-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="23152-366">您啟動的壓力與效能工具的每個實例, 都會立即開始登入使用者, 通常是每秒一個使用者的頻率。</span><span class="sxs-lookup"><span data-stu-id="23152-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="23152-367">該池的使用者登入速率峰值, 大約每秒12次。</span><span class="sxs-lookup"><span data-stu-id="23152-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="23152-368">這表示使用者仍在登入時, 您不應該同時啟動超過12個 LyncPerfTool 實例。</span><span class="sxs-lookup"><span data-stu-id="23152-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="23152-369">1000使用者大約需要20分鐘的時間, 以每秒完全登入。</span><span class="sxs-lookup"><span data-stu-id="23152-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="23152-370">解釋結果</span><span class="sxs-lookup"><span data-stu-id="23152-370">Interpreting the Results</span></span>
<span data-ttu-id="23152-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="23152-371"></span></span>

<span data-ttu-id="23152-372">商務用 Skype Server 2015 的應力和效能工具有許多計數器可協助您瞭解用戶端正在執行的工作, 以及是否遇到問題。</span><span class="sxs-lookup"><span data-stu-id="23152-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="23152-373">用戶端計數器</span><span class="sxs-lookup"><span data-stu-id="23152-373">Client Counters</span></span>

<span data-ttu-id="23152-374">每個執行中的 LyncPerfTool 實例都有個別的計數器實例。</span><span class="sxs-lookup"><span data-stu-id="23152-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="23152-375">每個實例都是以其進程識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="23152-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="23152-376">如果用戶端超載, 可能會發生其他問題。</span><span class="sxs-lookup"><span data-stu-id="23152-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="23152-377">若要避免這些問題:</span><span class="sxs-lookup"><span data-stu-id="23152-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="23152-378">監視用戶端電腦上的 CPU 和記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="23152-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="23152-379">如果 CPU 持續超過 90%, 請減少使用者數目。</span><span class="sxs-lookup"><span data-stu-id="23152-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="23152-380">當記憶體佔用量較高時, 如果頁面檔案開始耗盡空間, 可能會遇到問題。</span><span class="sxs-lookup"><span data-stu-id="23152-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="23152-381">確認確認費用未超出電腦的限制。</span><span class="sxs-lookup"><span data-stu-id="23152-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="23152-382">如果您正在執行記憶體限制, 請考慮增加頁面檔案大小或減少使用者數目。</span><span class="sxs-lookup"><span data-stu-id="23152-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="23152-383">以下是主要效能計數器的清單:</span><span class="sxs-lookup"><span data-stu-id="23152-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="23152-384">**一般資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-384">**General Information**</span></span>

|<span data-ttu-id="23152-385">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-385">**Performance Counter**</span></span>|<span data-ttu-id="23152-386">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-387">花費的時間 (以分鐘為單位)</span><span class="sxs-lookup"><span data-stu-id="23152-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="23152-388">進程開始之後所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="23152-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="23152-389">作用中端點</span><span class="sxs-lookup"><span data-stu-id="23152-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="23152-390">目前連線到伺服器的端點數目。</span><span class="sxs-lookup"><span data-stu-id="23152-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="23152-391">失敗的登錄</span><span class="sxs-lookup"><span data-stu-id="23152-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="23152-392">端點登入失敗的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="23152-393">登入嘗試</span><span class="sxs-lookup"><span data-stu-id="23152-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="23152-394">端點登入嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="23152-395">端點已中斷連接</span><span class="sxs-lookup"><span data-stu-id="23152-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="23152-396">已中斷連線的端點總數。</span><span class="sxs-lookup"><span data-stu-id="23152-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="23152-397">**目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-397">**Presence Information**</span></span>

|<span data-ttu-id="23152-398">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-398">**Performance Counter**</span></span>|<span data-ttu-id="23152-399">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-400">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="23152-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="23152-401">目前狀態變更嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-401">Total number of presence change attempts.</span></span> <span data-ttu-id="23152-402">針對不同類型的目前狀態變更, 請參閱 SetPresence (目前狀態類型) 通話效能計數器。</span><span class="sxs-lookup"><span data-stu-id="23152-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="23152-403">SetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="23152-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="23152-404">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="23152-405">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="23152-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="23152-406">[取得目前狀態] 要求嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="23152-407">GetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="23152-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="23152-408">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="23152-409">**通訊錄服務資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-409">**Address Book service information**</span></span>

|<span data-ttu-id="23152-410">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-410">**Performance Counter**</span></span>|<span data-ttu-id="23152-411">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-412">嘗試的 ABS 完整/增量檔案下載</span><span class="sxs-lookup"><span data-stu-id="23152-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="23152-413">已嘗試完整或增量檔案下載要求的總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-414">ABS 完整/Delta 檔案下載成功</span><span class="sxs-lookup"><span data-stu-id="23152-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="23152-415">已嘗試完整或增量檔案下載要求的總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-416">通訊錄 Web 查詢服務相關計數器</span><span class="sxs-lookup"><span data-stu-id="23152-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="23152-417">通訊錄檔案下載相關計數器。</span><span class="sxs-lookup"><span data-stu-id="23152-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="23152-418">嘗試 ABS 通話</span><span class="sxs-lookup"><span data-stu-id="23152-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="23152-419">嘗試的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="23152-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-420">ABS WS 通話成功</span><span class="sxs-lookup"><span data-stu-id="23152-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="23152-421">傳回成功回應代碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="23152-422">ABS WS 通話失敗</span><span class="sxs-lookup"><span data-stu-id="23152-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="23152-423">傳回錯誤回應代碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="23152-424">此類別包含用來監視通訊錄服務 (ABS) 檔案下載和通訊錄網頁查詢服務要求的計數器。</span><span class="sxs-lookup"><span data-stu-id="23152-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="23152-425">**通訊群組清單 (DL) 資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="23152-426">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-426">**Performance Counter**</span></span>|<span data-ttu-id="23152-427">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-428">已嘗試來電</span><span class="sxs-lookup"><span data-stu-id="23152-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="23152-429">嘗試的通訊群組清單展開 (DLX) web 服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="23152-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-430">通話成功</span><span class="sxs-lookup"><span data-stu-id="23152-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="23152-431">傳回成功回應代碼之 DLX web 服務要求的總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="23152-432">通話失敗</span><span class="sxs-lookup"><span data-stu-id="23152-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="23152-433">傳回錯誤回應代碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="23152-434">在啟用這些案例時, 以下所列的效能計數器會列示在所有的語音 IP (VoIP) 通話中, 包括對轉送伺服器、A/V 會議伺服器、邊緣伺服器、回應群組應用程式, 以及會議自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="23152-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="23152-435">**VoIP 基本資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="23152-436">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-436">**Performance Counter**</span></span>|<span data-ttu-id="23152-437">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-438">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="23152-438">Calls Active</span></span>  <br/> |<span data-ttu-id="23152-439">目前正在進行的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="23152-440">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="23152-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="23152-441">已終止的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="23152-442">拒絕通話</span><span class="sxs-lookup"><span data-stu-id="23152-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="23152-443">已拒絕的來電通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="23152-444">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="23152-445">已嘗試輸入/撥出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-446">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="23152-447">已建立的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="23152-448">呼叫已收到 NNN</span><span class="sxs-lookup"><span data-stu-id="23152-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="23152-449">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="23152-450">VoIP 傳遞率 (%)</span><span class="sxs-lookup"><span data-stu-id="23152-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="23152-451">已建立的通話總數/嘗試的通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="23152-452">**回應群組服務通話資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="23152-453">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-453">**Performance Counter**</span></span>|<span data-ttu-id="23152-454">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-455">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="23152-455">Calls Active</span></span>  <br/> |<span data-ttu-id="23152-456">回應群組應用程式的使用中通話總次數。</span><span class="sxs-lookup"><span data-stu-id="23152-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="23152-457">已嘗試來電</span><span class="sxs-lookup"><span data-stu-id="23152-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="23152-458">嘗試的通話總次數。</span><span class="sxs-lookup"><span data-stu-id="23152-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="23152-459">**立即訊息 (IM) 通話資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="23152-460">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-460">**Performance Counter**</span></span>|<span data-ttu-id="23152-461">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-462">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="23152-462">Calls Active</span></span>  <br/> |<span data-ttu-id="23152-463">正在進行內傳/撥出的立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="23152-464">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="23152-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="23152-465">已終止傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="23152-466">呼叫已收到 NNN</span><span class="sxs-lookup"><span data-stu-id="23152-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="23152-467">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="23152-468">接收/傳送的 IM 訊息</span><span class="sxs-lookup"><span data-stu-id="23152-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="23152-469">所有會話接收或傳送的訊息總數。</span><span class="sxs-lookup"><span data-stu-id="23152-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="23152-470">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="23152-471">嘗試的傳入/傳出立即訊息呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="23152-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-472">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="23152-473">已建立的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="23152-474">**App 共用呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="23152-475">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-475">**Performance Counter**</span></span>|<span data-ttu-id="23152-476">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-477">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="23152-477">Calls Active</span></span>  <br/> |<span data-ttu-id="23152-478">正在進行中傳入/傳出應用程式共用通話的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="23152-479">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="23152-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="23152-480">已終止的傳入/傳出應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="23152-481">呼叫已收到 NNN</span><span class="sxs-lookup"><span data-stu-id="23152-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="23152-482">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="23152-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="23152-483">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="23152-484">嘗試的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="23152-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-485">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="23152-486">已建立的傳入/傳出應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="23152-487">**CAA 通話資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-487">**CAA Call Information**</span></span>

|<span data-ttu-id="23152-488">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-488">**Performance Counter**</span></span>|<span data-ttu-id="23152-489">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-490">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="23152-490">Calls Active</span></span>  <br/> |<span data-ttu-id="23152-491">目前正在進行中的內送/出局公用電話網絡 (PSTN) 通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="23152-492">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="23152-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="23152-493">已終止的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="23152-494">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="23152-495">嘗試的傳入/傳出 PSTN 呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="23152-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="23152-496">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="23152-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="23152-497">已建立的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="23152-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="23152-498">**會議資訊**</span><span class="sxs-lookup"><span data-stu-id="23152-498">**Conference Information**</span></span>

|<span data-ttu-id="23152-499">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-499">**Performance Counter**</span></span>|<span data-ttu-id="23152-500">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-501">即時立即訊息會議</span><span class="sxs-lookup"><span data-stu-id="23152-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="23152-502">即時立即訊息會議的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="23152-503">活動音訊/視訊會議</span><span class="sxs-lookup"><span data-stu-id="23152-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="23152-504">正在進行的音訊/視頻 (A/V) 會議總數。</span><span class="sxs-lookup"><span data-stu-id="23152-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="23152-505">使用中的應用程式共用會議</span><span class="sxs-lookup"><span data-stu-id="23152-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="23152-506">正在進行的應用程式共用會議總數。</span><span class="sxs-lookup"><span data-stu-id="23152-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="23152-507">參與者人數</span><span class="sxs-lookup"><span data-stu-id="23152-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="23152-508">目前與會議連接的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="23152-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="23152-509">會議排程失敗</span><span class="sxs-lookup"><span data-stu-id="23152-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="23152-510">嘗試排程會議時失敗的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="23152-511">加入會議失敗</span><span class="sxs-lookup"><span data-stu-id="23152-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="23152-512">嘗試連線到會議時失敗的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="23152-513">**UCWA 用戶端計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="23152-514">**效能計數器**</span><span class="sxs-lookup"><span data-stu-id="23152-514">**Performance Counter**</span></span>|<span data-ttu-id="23152-515">**說明**</span><span class="sxs-lookup"><span data-stu-id="23152-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23152-516">成功的 IMMCU 連接總數</span><span class="sxs-lookup"><span data-stu-id="23152-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="23152-517">已加入之立即訊息會議的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="23152-518">成功的 DMCU 連接總數</span><span class="sxs-lookup"><span data-stu-id="23152-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="23152-519">已加入/V 會議的總數。</span><span class="sxs-lookup"><span data-stu-id="23152-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

