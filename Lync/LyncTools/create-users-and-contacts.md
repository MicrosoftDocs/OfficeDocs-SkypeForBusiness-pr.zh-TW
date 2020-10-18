---
title: 建立使用者和連絡人
description: 建立使用者和連絡人。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e45bb1aa737dd8287be15ae72ece2e35a346af1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573079"
---
# <a name="create-users-and-contacts"></a><span data-ttu-id="205c8-103">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="205c8-103">Create Users and Contacts</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="205c8-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="205c8-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="205c8-105">您必須使用 Lync Server 2013 使用者布建工具 ( # A0) 來建立使用者和連絡人，以準備壓力和效能負載測試。</span><span class="sxs-lookup"><span data-stu-id="205c8-105">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="205c8-106">以下是您在閱讀本主題時，可能會發現的術語和定義的清單。</span><span class="sxs-lookup"><span data-stu-id="205c8-106">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="205c8-107">組織單位– Active Directory 網域服務組織單位 (OU) 。</span><span class="sxs-lookup"><span data-stu-id="205c8-107">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="205c8-108">同盟/跨集區–會讓使用者能夠與其他立即訊息 (IM) 服務（例如 Internet 服務、AOL®和 Yahoo®的 MSN 網路）進行通訊的使用者 \! 。</span><span class="sxs-lookup"><span data-stu-id="205c8-108">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="205c8-109">通訊群組清單– Active Directory 網域服務中包含 Active Directory 網域服務使用者清單的物件，用來啟動與一組人員的通訊。</span><span class="sxs-lookup"><span data-stu-id="205c8-109">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="205c8-110">位置資訊服務– Lync Server 2013 服務，啟用並設定每個電話時，可對增強型 9-1-1 (E9-1-1) 服務的實體位置進行檢索。</span><span class="sxs-lookup"><span data-stu-id="205c8-110">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="205c8-111">美國電話號碼–指派給使用者的電話號碼，除了用於路由輸入和撥出電話及反向號碼查閱 (RNL) 的 SIP URI 之外。</span><span class="sxs-lookup"><span data-stu-id="205c8-111">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="205c8-112">使用 UserProvisioningTool.exe 建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="205c8-112">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="205c8-113">您必須使用 Lync Server 使用者布建工具建立使用者和連絡人，以進行負載模擬。</span><span class="sxs-lookup"><span data-stu-id="205c8-113">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="205c8-114">Lync Server 使用者布建工具隨 Lync Server 壓力和效能工具套件一起安裝。</span><span class="sxs-lookup"><span data-stu-id="205c8-114">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="205c8-115">請確定已在前端伺服器或 Standard Edition server 上執行套件安裝程式 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="205c8-115">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="205c8-116">在前端伺服器或 Standard Edition Server 上執行檔案 UserProvisioningTool.exe (，以啟動 Lync Server 使用者布建工具，) 位於% InstalledDirectory% LyncStressAndPerfTool \\ LyncStress。</span><span class="sxs-lookup"><span data-stu-id="205c8-116">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="205c8-117">您必須以 Domain Admins 安全性群組成員的身分登入，才能執行 UserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="205c8-117">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="205c8-118">您必須執行此內容，因為 UserProvisioningTool.exe 將會建立及設定新的 Active Directory 網域服務使用者。</span><span class="sxs-lookup"><span data-stu-id="205c8-118">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="205c8-119">當您建立大量使用者 (10000 或更) 時，請從高端電腦執行 UserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="205c8-119">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="205c8-120">請注意，網域控制站也會在建立使用者時經歷高負載。</span><span class="sxs-lookup"><span data-stu-id="205c8-120">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="205c8-121">當 Lync Server 使用者布建工具開啟時， **按一下 [設定]，然後** 選取 [ **載入**設定]。</span><span class="sxs-lookup"><span data-stu-id="205c8-121">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="205c8-122">若要開始設定使用者和連絡人，請載入套件中所含的預設檔案 SampleData.xml。</span><span class="sxs-lookup"><span data-stu-id="205c8-122">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="205c8-123">這將會預設包含您的系統需要修訂之範例資料的欄位。</span><span class="sxs-lookup"><span data-stu-id="205c8-123">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="205c8-124">如果您有預先設定的 XML 檔案，而該檔案已包含自訂設定，請改為載入該檔案。</span><span class="sxs-lookup"><span data-stu-id="205c8-124">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="205c8-125">填寫 Lync Server 使用者布建工具中的欄位，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="205c8-125">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="205c8-126">![[使用者建立] 索引標籤。](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "[使用者建立] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="205c8-126">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="205c8-127">若要設定伺服器選項，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="205c8-127">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="205c8-128">在 [ **前端集區 FQDN**] 中，輸入您要主控使用者之 Standard Edition Server 或前端集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="205c8-128">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="205c8-129">在 [ **使用者名稱首碼**] 中，輸入您要用來建立用於測試目的之使用者名稱的前置詞。</span><span class="sxs-lookup"><span data-stu-id="205c8-129">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="205c8-130">在 [ **密碼**] 中，指定要套用於所有測試使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="205c8-130">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="205c8-131">在 [ **SIP 網域**] 中，輸入要用於測試使用者之 SIP URIs (統一資源識別項) 的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="205c8-131">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="205c8-132">在 [ **帳戶網域**] 中，輸入您目前 Active Directory 網域服務網域的功能變數名稱，您要在此網域中建立測試使用者。</span><span class="sxs-lookup"><span data-stu-id="205c8-132">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="205c8-133">在 [ **組織單位**] 中，輸入您要在其中建立使用者物件的 Active Directory 網域服務 OU 名稱。</span><span class="sxs-lookup"><span data-stu-id="205c8-133">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="205c8-134">如果 OU 不存在，則會建立該 OU。</span><span class="sxs-lookup"><span data-stu-id="205c8-134">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="205c8-135">在 [ **電話區號**] 中，輸入將用於測試使用者帳戶的三位數區功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="205c8-135">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="205c8-136">請確定電話區號不會與 Active Directory 網域服務中的任何其他使用者區功能變數代碼衝突。</span><span class="sxs-lookup"><span data-stu-id="205c8-136">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="205c8-137">如果您想要啟用適用于 Enterprise Voice 的測試使用者，請選取 [ **啟用語音功能** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="205c8-137">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="205c8-138">在 [ **使用者數目**] 中，指定您要建立的測試使用者總數。</span><span class="sxs-lookup"><span data-stu-id="205c8-138">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="205c8-139">在 [ **起始索引**] 中，指定要用來做為使用者名稱前置詞尾碼的開始號碼。</span><span class="sxs-lookup"><span data-stu-id="205c8-139">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="205c8-140">建立使用者按鈕</span><span class="sxs-lookup"><span data-stu-id="205c8-140">Create Users Button</span></span>

<span data-ttu-id="205c8-141">當您按一下 [建立使用者] 按鈕時，它會驗證所有的輸入參數。</span><span class="sxs-lookup"><span data-stu-id="205c8-141">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="205c8-142">如果有任何驗證錯誤，它會提示您修正輸入值。</span><span class="sxs-lookup"><span data-stu-id="205c8-142">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="205c8-143">如果所有輸入值都是正確的，將會在 Active Directory 網域服務中開始建立使用者。</span><span class="sxs-lookup"><span data-stu-id="205c8-143">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="205c8-144">進度列會出現在此表單的底部。</span><span class="sxs-lookup"><span data-stu-id="205c8-144">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="205c8-145">建議您不要在進度列處於作用中時關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="205c8-145">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="205c8-146">使用者建立過程很慢。</span><span class="sxs-lookup"><span data-stu-id="205c8-146">User Creation is a slow process.</span></span> <span data-ttu-id="205c8-147">可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="205c8-147">It can take several minutes.</span></span> <span data-ttu-id="205c8-148">如果使用者數目非常大，則程式甚至可能需要數小時的時間。</span><span class="sxs-lookup"><span data-stu-id="205c8-148">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="205c8-149">如果使用者已存在，則會以任何變更更新。</span><span class="sxs-lookup"><span data-stu-id="205c8-149">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="205c8-150">您可以驗證使用者是否已以範圍中的其中一位使用者的身分登入來建立。</span><span class="sxs-lookup"><span data-stu-id="205c8-150">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="205c8-151">使用使用者前置詞、使用者號碼和 @sipDomain 做為使用者名稱 (例如，LyncUser10@contoso.net) ，以及指定的密碼。</span><span class="sxs-lookup"><span data-stu-id="205c8-151">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="205c8-152">[刪除使用者] 按鈕</span><span class="sxs-lookup"><span data-stu-id="205c8-152">Delete Users Button</span></span>

<span data-ttu-id="205c8-153">當您按一下 [刪除使用者] 按鈕時，它會驗證所有的輸入參數。</span><span class="sxs-lookup"><span data-stu-id="205c8-153">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="205c8-154">如果有任何驗證錯誤，它會提示您修正輸入值。</span><span class="sxs-lookup"><span data-stu-id="205c8-154">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="205c8-155">如果所有輸入值都是正確的，將會開始停用或刪除 Active Directory 網域服務中的使用者。</span><span class="sxs-lookup"><span data-stu-id="205c8-155">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="205c8-156">進度列會出現在此表單的底部。</span><span class="sxs-lookup"><span data-stu-id="205c8-156">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="205c8-157">建議您不要在進度列處於作用中時關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="205c8-157">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="205c8-158">只支援 U.S. 格式的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="205c8-158">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="205c8-159">電話號碼一定會指派給使用者，而由 UserProvisioningTool.exe 所建立的所有使用者都是針對 Enterprise Voice 啟用。</span><span class="sxs-lookup"><span data-stu-id="205c8-159">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="205c8-160">使用電話號碼的任何案例（如會議自動語音應答或 UC-PSTN 通話）都會使用此電話號碼來正確地路由通話。</span><span class="sxs-lookup"><span data-stu-id="205c8-160">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="205c8-161">因此，每個使用者都必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="205c8-161">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="205c8-162">如果您必須建立使用者兩次，除非您使用不同的區號，或是先前的使用者已使用 <STRONG>get-csuser 指令程式</STRONG> 停用，否則命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="205c8-162">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="205c8-163">在您建立連絡人之前，必須先完成從 [使用者] 索引標籤執行的使用者複寫。如果您剛剛建立使用者，必須等到 Lync Server 複寫完成，並填入資料庫中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="205c8-163">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="205c8-164">如果使用者尚未完成複製，您會看到錯誤。</span><span class="sxs-lookup"><span data-stu-id="205c8-164">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="205c8-165">如果已啟動 Lync Server 2013 前端服務，或在最後一個使用者上成功執行 <STRONG>Get-CsUser</STRONG> Cmdlet，您就會知道使用者何時完成複製。</span><span class="sxs-lookup"><span data-stu-id="205c8-165">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="205c8-166">[建立連絡人] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="205c8-166">Contacts Creation Tab</span></span>

<span data-ttu-id="205c8-167">[連絡人建立] 索引標籤可讓您指定使用者連絡人的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="205c8-167">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="205c8-168">![[建立連絡人] 索引標籤。](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "[建立連絡人] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="205c8-168">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="205c8-169">若要設定使用者的連絡人，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="205c8-169">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="205c8-170">在 [每位使用者的平均連絡方式] 中，指定每位使用者的連絡人清單中所填入的連絡人平均人數。</span><span class="sxs-lookup"><span data-stu-id="205c8-170">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="205c8-171">如果您想要為每位使用者建立相同數目的連絡人，請選取 [固定] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="205c8-171">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="205c8-172">如果您想要改變為使用者建立的連絡人數目，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="205c8-172">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="205c8-173">在 [每位使用者的平均連絡人群組] 中，指定每位使用者的連絡人群組數目。</span><span class="sxs-lookup"><span data-stu-id="205c8-173">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="205c8-174">此號碼必須小於每位使用者的平均連絡人數目。</span><span class="sxs-lookup"><span data-stu-id="205c8-174">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="205c8-175">在 [同盟/跨集區連絡人百分比] 中，指定介於0到100之間的數位。</span><span class="sxs-lookup"><span data-stu-id="205c8-175">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="205c8-176">這則會以同盟使用者的連絡方式建立此百分比。</span><span class="sxs-lookup"><span data-stu-id="205c8-176">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="205c8-177">在 [同盟/跨集區使用者前置詞] 中，指定將新增至本機使用者連絡人清單的同盟使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="205c8-177">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="205c8-178">在 [同盟/跨集區使用者 SIP 網域] 中，指定同盟使用者的 SIP 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="205c8-178">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="205c8-179">建立連絡人時，不應該登入任何使用者。</span><span class="sxs-lookup"><span data-stu-id="205c8-179">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="205c8-180">在 [使用者建立] 索引標籤中，確認參數是否正確。</span><span class="sxs-lookup"><span data-stu-id="205c8-180">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="205c8-181">在 [使用者建立] 索引標籤中，將建立連絡人的使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="205c8-181">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="205c8-182">按一下 [建立連絡人] 以開始建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="205c8-182">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="205c8-183">此程式可能需要數分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="205c8-183">This process can take several minutes.</span></span> <span data-ttu-id="205c8-184">完成後，會出現一個對話方塊，其中會出現「作業已順利完成」的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="205c8-184">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="205c8-185">您可以使用 [使用者建立] 索引標籤上所建立的使用者來驗證所建立的連絡人。</span><span class="sxs-lookup"><span data-stu-id="205c8-185">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="205c8-186">建立連絡人之後，此工具將會重新開機目標集區中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="205c8-186">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="205c8-187">這可能需要較長 (2) 小時的時間，前端伺服器才能啟動，視這個作業建立的連絡人數目而定。</span><span class="sxs-lookup"><span data-stu-id="205c8-187">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="205c8-188">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="205c8-188">Distribution List</span></span>

<span data-ttu-id="205c8-189">Lync Server 2013 壓力和效能工具其中一項功能是在 Lync 2013 中模擬通訊群組清單 (DL) 擴充功能。</span><span class="sxs-lookup"><span data-stu-id="205c8-189">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="205c8-190">如果您不想要在 UserProvisioningTool 中啟用 DL 擴充，可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="205c8-190">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="205c8-191">![[通訊群組清單建立] 索引標籤。](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "[通訊群組清單建立] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="205c8-191">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="205c8-192">[通訊群組清單] 索引標籤可讓您建立壓力和效能工具將用於通訊群組清單擴充功能的 DLs。</span><span class="sxs-lookup"><span data-stu-id="205c8-192">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="205c8-193">在建立 DLs 之前，必須先安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="205c8-193">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="205c8-194">您必須已執行 Lync Server 2013 ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="205c8-194">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="205c8-195">否則，DL 屬性不存在於 Active Directory 網域服務架構中，而且工具將無法建立 DLs。</span><span class="sxs-lookup"><span data-stu-id="205c8-195">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="205c8-196">若要設定通訊群組清單，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="205c8-196">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="205c8-197">在 [通訊群組清單數目] 中，指定您要建立的 DLs 總數。</span><span class="sxs-lookup"><span data-stu-id="205c8-197">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="205c8-198"> (建議您從) 的使用者數目開始。</span><span class="sxs-lookup"><span data-stu-id="205c8-198">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="205c8-199">其編號為從0到 n-1。</span><span class="sxs-lookup"><span data-stu-id="205c8-199">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="205c8-200">在 [通訊群組清單首碼] 中，指定 DLs 所擁有的前置詞。</span><span class="sxs-lookup"><span data-stu-id="205c8-200">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="205c8-201">例如，如果您指定 100 DLs 和首碼 testDL，則 DLs 會命名為 testDL0、testDL1 等等，而不是透過 testDL99。</span><span class="sxs-lookup"><span data-stu-id="205c8-201">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="205c8-202">在 Dist 的 [最少成員] 清單中，指定每個通訊群組清單中要新增的使用者數目下限。</span><span class="sxs-lookup"><span data-stu-id="205c8-202">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="205c8-203">在 [Dist] 中的 [最大成員] 清單中，指定每個通訊群組清單中要新增的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="205c8-203">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="205c8-204">建立通訊群組清單按鈕</span><span class="sxs-lookup"><span data-stu-id="205c8-204">Create Distribution Lists Button</span></span>

<span data-ttu-id="205c8-205">當您按一下 [建立通訊群組清單] 按鈕時，此工具會查詢 Active Directory 網域服務，以查看符合首碼和號碼的通訊群組清單是否已存在。</span><span class="sxs-lookup"><span data-stu-id="205c8-205">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="205c8-206">工具只會建立尚未存在的專案。</span><span class="sxs-lookup"><span data-stu-id="205c8-206">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="205c8-207">將成員新增至這些新建立的通訊群組清單時，會從 [使用者建立] 索引標籤上指定的範圍內挑選使用者。</span><span class="sxs-lookup"><span data-stu-id="205c8-207">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="205c8-208">位置資訊服務的 [配置] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="205c8-208">Location Info Service Config Tab</span></span>

<span data-ttu-id="205c8-209">Lync Server 2013 壓力和效能工具其中一項功能是針對位置資訊服務產生偽設定檔。</span><span class="sxs-lookup"><span data-stu-id="205c8-209">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="205c8-210">位置資訊服務通常對伺服器的效能沒有任何重大影響。</span><span class="sxs-lookup"><span data-stu-id="205c8-210">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="205c8-211">![[位置資訊服務 Config] 索引標籤。](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "[位置資訊服務 Config] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="205c8-211">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="205c8-212">如果您選擇測試此功能，您可以填入表單中所述的值，然後按一下 [產生 .LIS 的 Config Files] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="205c8-212">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="205c8-213">它會產生稱為 .LIS \_Subnet.csv、.lis \_Switches.csv、.Lis \_Ports.csv 和 .LISWAP.csv 的 CSV 檔案 \_ 。</span><span class="sxs-lookup"><span data-stu-id="205c8-213">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="205c8-214">然後，您可以將這些 CSV 檔案匯入到 .LIS 資料庫，方法是使用 **CsLisSubnet** 指令程式、 **CsLisSwitch** 指令程式、set- **CsLisPort** 指令程式，以及 **設定 CsWirelessAccessPoint** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="205c8-214">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

