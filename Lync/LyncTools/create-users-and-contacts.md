---
title: 建立使用者和連絡人
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f09ac6fd667b77b47e27ec9fb9caac44b9a13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="ede94-102">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="ede94-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ede94-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ede94-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ede94-104">您必須使用 Lync Server 2013 使用者提供工具（UserProvisioningTool）來建立使用者和連絡人，才能準備壓力與效能負載測試。</span><span class="sxs-lookup"><span data-stu-id="ede94-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="ede94-105">以下是您在閱讀本主題時可能會發現的字詞和定義的清單。</span><span class="sxs-lookup"><span data-stu-id="ede94-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="ede94-106">組織單位-Active Directory 網域服務組織單位（OU）。</span><span class="sxs-lookup"><span data-stu-id="ede94-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="ede94-107">[同盟/跨區]：可讓使用者從其他立即訊息（IM）服務（例如 MSN 網際網路服務、AOL®和® Yahoo\!）與使用者通訊的使用者。</span><span class="sxs-lookup"><span data-stu-id="ede94-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="ede94-108">通訊群組清單： Active Directory 網域服務中包含 Active Directory 網域服務使用者清單的物件，用於啟動與人員群組的通訊。</span><span class="sxs-lookup"><span data-stu-id="ede94-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="ede94-109">位置資訊服務-Lync Server 2013 服務（在每個手機上啟用和設定時）可讓您檢索增強9-1-1 （E9-1）服務的物理位置。</span><span class="sxs-lookup"><span data-stu-id="ede94-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="ede94-110">美國電話號碼：指派給使用者的電話號碼，以及用於路由輸入和撥出通話與反向號碼查閱（RNL）的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="ede94-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="ede94-111">使用 UserProvisioningTool 建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="ede94-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="ede94-112">您必須使用 Lync Server 使用者預配工具來建立負載模擬的使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="ede94-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="ede94-113">Lync server 使用者預配工具是隨 Lync Server 壓力和效能工具套件一起安裝。</span><span class="sxs-lookup"><span data-stu-id="ede94-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="ede94-114">請確定已在前端伺服器或標準版伺服器上執行套件安裝程式（CapacityPlanningTool）。</span><span class="sxs-lookup"><span data-stu-id="ede94-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="ede94-115">在前端伺服器或標準版伺服器上執行檔案 UserProvisioningTool （位於% InstalledDirectory% LyncStressAndPerfTool\\LyncStress），以啟動 Lync Server 使用者預配工具。</span><span class="sxs-lookup"><span data-stu-id="ede94-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ede94-116">您必須以網域管理員安全性群組的成員身分登入，才能執行 UserProvisioningTool。</span><span class="sxs-lookup"><span data-stu-id="ede94-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="ede94-117">您必須從這個內容執行，因為 UserProvisioningTool 會建立並設定新的 Active Directory 網域服務使用者。</span><span class="sxs-lookup"><span data-stu-id="ede94-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ede94-118">當您建立有大量的使用者（10000或更多）時，請從高端電腦執行 UserProvisioningTool。</span><span class="sxs-lookup"><span data-stu-id="ede94-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="ede94-119">請注意，在建立使用者時，網網域控制站也會遇到高負載。</span><span class="sxs-lookup"><span data-stu-id="ede94-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="ede94-120">當 Lync Server 使用者提供工具開啟時 **，按一下 [設定]，然後**選取 [**載入**設定]。</span><span class="sxs-lookup"><span data-stu-id="ede94-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="ede94-121">若要開始配置使用者和連絡人，請載入套件中包含的預設檔案 SampleData .xml。</span><span class="sxs-lookup"><span data-stu-id="ede94-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="ede94-122">這將會針對您的系統所需修正的範例資料來預填入欄位。</span><span class="sxs-lookup"><span data-stu-id="ede94-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="ede94-123">如果您有預先配置的 XML 檔案，而該檔案已包含自訂的設定，請改為載入該檔案。</span><span class="sxs-lookup"><span data-stu-id="ede94-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="ede94-124">在 Lync Server 使用者預配工具中填入欄位，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="ede94-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="ede94-125">[![使用者建立]]索引標籤。[(images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "使用者建立]")索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ede94-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="ede94-126">若要設定伺服器選項，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="ede94-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="ede94-127">在 [**前端池 FQDN**] 中，輸入您要主持使用者之標準版伺服器或前端池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="ede94-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="ede94-128">在 [**使用者名稱首碼**] 中，輸入您要用來建立使用者名稱以供測試之使用的首碼。</span><span class="sxs-lookup"><span data-stu-id="ede94-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="ede94-129">在 [**密碼**] 中，指定將針對所有測試使用者帳戶套用的密碼。</span><span class="sxs-lookup"><span data-stu-id="ede94-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="ede94-130">在**SIP 網域**中，輸入要用於測試使用者 sip Uri （統一資源識別項）的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="ede94-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="ede94-131">在 [**帳戶網域**] 中，輸入您目前 Active Directory 網域服務網域的功能變數名稱（您要在其中建立測試使用者）。</span><span class="sxs-lookup"><span data-stu-id="ede94-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="ede94-132">在 [**組織單位**] 中，輸入您要在其中建立使用者物件之 Active Directory 網域服務組織單位的名稱。</span><span class="sxs-lookup"><span data-stu-id="ede94-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="ede94-133">如果 OU 不存在，就會建立它。</span><span class="sxs-lookup"><span data-stu-id="ede94-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="ede94-134">在 [**電話區功能變數代碼**] 中，輸入要用於測試使用者帳戶的三位數區功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="ede94-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="ede94-135">請確定電話區代碼不會與 Active Directory 網域服務中其他使用者的區功能變數代碼發生衝突。</span><span class="sxs-lookup"><span data-stu-id="ede94-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="ede94-136">如果您想要啟用企業語音測試使用者，請選取 [**已啟用語音**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ede94-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="ede94-137">在 [**使用者數目**] 中，指定您要建立的測試使用者總數。</span><span class="sxs-lookup"><span data-stu-id="ede94-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="ede94-138">在 [**起始索引**] 中，指定要用來做為使用者名稱首碼尾碼的起始數位。</span><span class="sxs-lookup"><span data-stu-id="ede94-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="ede94-139">[建立使用者] 按鈕</span><span class="sxs-lookup"><span data-stu-id="ede94-139">Create Users Button</span></span>

<span data-ttu-id="ede94-140">當您按一下 [建立使用者] 按鈕時，它會驗證所有輸入參數。</span><span class="sxs-lookup"><span data-stu-id="ede94-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="ede94-141">如果有任何驗證錯誤，就會提示您修正輸入值。</span><span class="sxs-lookup"><span data-stu-id="ede94-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="ede94-142">如果所有輸入值都是正確的，則會在 Active Directory 網域服務中開始建立使用者。</span><span class="sxs-lookup"><span data-stu-id="ede94-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="ede94-143">進度列會出現在此表單的底部。</span><span class="sxs-lookup"><span data-stu-id="ede94-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="ede94-144">我們建議您不要在進度列處於作用中時關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="ede94-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="ede94-145">使用者建立速度緩慢。</span><span class="sxs-lookup"><span data-stu-id="ede94-145">User Creation is a slow process.</span></span> <span data-ttu-id="ede94-146">可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="ede94-146">It can take several minutes.</span></span> <span data-ttu-id="ede94-147">如果使用者數量非常大，程式甚至可能需要幾個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="ede94-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="ede94-148">如果使用者已經存在，則會使用任何變更進行更新。</span><span class="sxs-lookup"><span data-stu-id="ede94-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="ede94-149">您可以透過以範圍中的一位使用者的身分登入，來驗證使用者是否已建立。</span><span class="sxs-lookup"><span data-stu-id="ede94-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="ede94-150">使用使用者的前置詞、使用者編號及 @sipDomain 作為使用者名稱（例如，LyncUser10@contoso.net），以及指定的密碼。</span><span class="sxs-lookup"><span data-stu-id="ede94-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="ede94-151">[刪除使用者] 按鈕</span><span class="sxs-lookup"><span data-stu-id="ede94-151">Delete Users Button</span></span>

<span data-ttu-id="ede94-152">當您按一下 [刪除使用者] 按鈕時，它會驗證所有輸入參數。</span><span class="sxs-lookup"><span data-stu-id="ede94-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="ede94-153">如果有任何驗證錯誤，就會提示您修正輸入值。</span><span class="sxs-lookup"><span data-stu-id="ede94-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="ede94-154">如果所有輸入值都是正確的，就會開始停用並刪除 Active Directory 網域服務中的使用者。</span><span class="sxs-lookup"><span data-stu-id="ede94-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="ede94-155">進度列會出現在此表單的底部。</span><span class="sxs-lookup"><span data-stu-id="ede94-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="ede94-156">我們建議您不要在進度列處於作用中時關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="ede94-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="ede94-157">僅支援美國格式的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ede94-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="ede94-158">電話號碼永遠會指派給使用者，而由 UserProvisioningTool 所建立的所有使用者都可以使用企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="ede94-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="ede94-159">使用電話號碼（例如會議自動語音應答或 UC PSTN 通話）的任何案例，都可以使用此電話號碼來正確路由通話。</span><span class="sxs-lookup"><span data-stu-id="ede94-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="ede94-160">基於這個原因，每個使用者都必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ede94-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="ede94-161">如果您必須建立使用者兩次，除非您使用不同的區號，或使用<STRONG>Disable move-csuser</STRONG> Cmdlet 來停用先前的使用者，否則命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ede94-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="ede94-162">在您建立連絡人之前，您必須先完成從 [使用者] 索引標籤執行的使用者複製。如果您剛剛建立使用者，您必須等到 Lync Server 複製完成，然後填入資料庫中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ede94-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="ede94-163">如果使用者尚未完成複製，您會看到錯誤。</span><span class="sxs-lookup"><span data-stu-id="ede94-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="ede94-164">如果 Lync Server 2013 前端服務已啟動，或在最後一個使用者上成功執行<STRONG>move-csuser</STRONG> Cmdlet，您就會知道使用者已完成複製的時間。</span><span class="sxs-lookup"><span data-stu-id="ede94-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="ede94-165">連絡人 [建立] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ede94-165">Contacts Creation Tab</span></span>

<span data-ttu-id="ede94-166">[連絡人建立] 索引標籤可讓您指定使用者連絡人的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ede94-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="ede94-167">![連絡人 [建立]]索引標籤。(images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "連絡人 [建立]")索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ede94-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="ede94-168">若要設定使用者的連絡人，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="ede94-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="ede94-169">在 [每位使用者平均連絡人] 中，指定要在連絡人清單中為每位使用者填入的連絡人平均數。</span><span class="sxs-lookup"><span data-stu-id="ede94-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="ede94-170">如果您想要為每位使用者建立同等數量的連絡人，請選取 [固定] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ede94-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="ede94-171">如果您想要變更為使用者建立的連絡人數目，請清除該核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ede94-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="ede94-172">在 [每位使用者的平均連絡人群組] 中，指定每位使用者的連絡人群組數量。</span><span class="sxs-lookup"><span data-stu-id="ede94-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="ede94-173">這個數位必須小於每位使用者的平均連絡人數。</span><span class="sxs-lookup"><span data-stu-id="ede94-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="ede94-174">在 [聯盟/跨池連絡人百分比] 中，指定0到100之間的數位。</span><span class="sxs-lookup"><span data-stu-id="ede94-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="ede94-175">系統會使用聯盟使用者建立此連絡人的百分比。</span><span class="sxs-lookup"><span data-stu-id="ede94-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="ede94-176">在 [同盟/跨池使用者首碼] 中，指定將新增至本機使用者連絡人清單的聯盟使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="ede94-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="ede94-177">在 [聯盟/跨池使用者 SIP 網域] 中，指定聯盟使用者的 SIP 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="ede94-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ede94-178">無法在建立連絡人時登入任何使用者。</span><span class="sxs-lookup"><span data-stu-id="ede94-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="ede94-179">在 [使用者建立] 索引標籤中，確認參數正確無誤。</span><span class="sxs-lookup"><span data-stu-id="ede94-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="ede94-180">系統會從 [使用者建立] 索引標籤取得連絡人所要建立的使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="ede94-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="ede94-181">按一下 [建立連絡人]，開始建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="ede94-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="ede94-182">這個程式可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="ede94-182">This process can take several minutes.</span></span> <span data-ttu-id="ede94-183">完成之後，會出現一個對話方塊，其中顯示 [作業已順利完成] 訊息。</span><span class="sxs-lookup"><span data-stu-id="ede94-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="ede94-184">您可以從以使用者 [建立] 索引標籤建立的使用者身分登入，以驗證所建立的連絡人。</span><span class="sxs-lookup"><span data-stu-id="ede94-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ede94-185">建立連絡人之後，此工具會重新開機目標池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ede94-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="ede94-186">前端伺服器可能需要較長時間（最多2小時）才能啟動，視這個作業建立的連絡人數量而定。</span><span class="sxs-lookup"><span data-stu-id="ede94-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="ede94-187">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="ede94-187">Distribution List</span></span>

<span data-ttu-id="ede94-188">Lync Server 2013 應力和效能工具的其中一個功能，就是模擬 Lync 2013 中的通訊群組清單（DL）擴充功能。</span><span class="sxs-lookup"><span data-stu-id="ede94-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="ede94-189">如果您不打算在 UserProvisioningTool 中啟用 DL 延伸，您可以略過這個步驟。</span><span class="sxs-lookup"><span data-stu-id="ede94-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="ede94-190">[![通訊群組清單建立]]索引標籤。[(images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "通訊群組清單建立]")索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ede94-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="ede94-191">[通訊群組清單] 索引標籤可讓您建立使用壓力與效能工具來進行通訊群組清單擴充功能的 Dl。</span><span class="sxs-lookup"><span data-stu-id="ede94-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="ede94-192">在建立 Dl 之前，必須先安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ede94-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="ede94-193">您必須已執行 Lync Server 2013 ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="ede94-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="ede94-194">否則，DL 屬性不會存在於 Active Directory 網域服務架構中，且工具將無法建立 DLs。</span><span class="sxs-lookup"><span data-stu-id="ede94-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="ede94-195">若要設定通訊群組清單，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="ede94-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="ede94-196">在 [通訊群組清單數目] 中，指定您要建立的 Dl 總數。</span><span class="sxs-lookup"><span data-stu-id="ede94-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="ede94-197">（我們建議您從兩個使用者數開始）。</span><span class="sxs-lookup"><span data-stu-id="ede94-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="ede94-198">它們的編號從0到 n-1。</span><span class="sxs-lookup"><span data-stu-id="ede94-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="ede94-199">在通訊群組清單首碼中，指定 Dl 將擁有的前置詞。</span><span class="sxs-lookup"><span data-stu-id="ede94-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="ede94-200">例如，如果您指定 100 DLs 及 testDL 的首碼，系統會將 Dl 命名為 testDL0，testDL1，依此類推，直到 testDL99。</span><span class="sxs-lookup"><span data-stu-id="ede94-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="ede94-201">在 [Dist] 中的 [最小成員] 清單中，指定要在每個通訊群組清單中新增的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="ede94-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="ede94-202">在 [Dist] 中的 [最大成員數] 清單中，指定要在每個通訊群組清單中新增的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="ede94-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="ede94-203">建立通訊群組清單按鈕</span><span class="sxs-lookup"><span data-stu-id="ede94-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="ede94-204">當您按一下 [建立通訊群組清單] 按鈕時，該工具會查詢 Active Directory 網域服務，以查看是否有符合該首碼和數位的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="ede94-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="ede94-205">此工具只會建立尚不存在的專案。</span><span class="sxs-lookup"><span data-stu-id="ede94-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="ede94-206">將成員新增到這些新建立的通訊群組清單時，會從 [使用者建立] 索引標籤上指定的範圍中挑選使用者。</span><span class="sxs-lookup"><span data-stu-id="ede94-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="ede94-207">位置資訊服務 [配置] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ede94-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="ede94-208">Lync Server 2013 應力和效能工具的其中一個功能，就是產生位置資訊服務的虛擬設定檔。</span><span class="sxs-lookup"><span data-stu-id="ede94-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="ede94-209">位置資訊服務通常不會對伺服器產生任何重要的效能影響。</span><span class="sxs-lookup"><span data-stu-id="ede94-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="ede94-210">![位置資訊服務 [配置]]索引標籤。(images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "位置資訊服務 [配置]")索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ede94-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="ede94-211">如果您選擇要測試這項功能，您可以在表單中填入所提及的值，然後按一下 [產生 IIS 配置檔案] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ede94-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="ede94-212">它將會產生名為 .LIS\_子網 .CSV、.lis\_開關 .csv、.LIS\_埠 .csv 和 .lis\_的 WAP .csv 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="ede94-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="ede94-213">接著，您可以使用**CsLisSubnet** Cmdlet、 **CsLisSwitch** Cmdlet、 **set CsLisPort** Cmdlet 以及**SET-CsWirelessAccessPoint** Cmdlet，將這些 CSV 檔案匯入到 iis 資料庫。</span><span class="sxs-lookup"><span data-stu-id="ede94-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

