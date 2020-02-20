---
title: 建立使用者和連絡人
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f30737ebf721d17059418c690e678f69f0296a6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="4f3b7-102">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="4f3b7-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f3b7-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="4f3b7-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4f3b7-104">您必須使用 Lync Server 2013 使用者佈建工具 (UserProvisioningTool.exe) 來建立使用者和連絡人以準備壓力及效能負載測試。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="4f3b7-105">以下是可能有幫助您閱讀透過本主題的詞彙與定義的清單。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="4f3b7-106">組織單位 – Active Directory 網域服務組織單位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="4f3b7-107">同盟 / 跨集區-會啟用的使用者從其他立即訊息 (IM) 服務，例如網際網路服務、 AOL®，和 Yahoo MSN 網路進行通訊的使用者\!®。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="4f3b7-108">通訊群組清單 – 包含 Active Directory 網域服務使用者，用來啟動與組群的人通訊清單的 Active Directory 網域服務中的物件。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="4f3b7-109">位置資訊服務 – 可時啟用及設定每個電話，讓您擷取增強型 9-1-1 (E9-1-1) 服務的實體位置的 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="4f3b7-110">美國電話號碼 – 指派給使用者，除了用於路由內送和外送呼叫的 SIP URI 和反向號碼查閱 (RNL) 的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="4f3b7-111">使用 UserProvisioningTool.exe 建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="4f3b7-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="4f3b7-112">您必須使用 Lync Server 使用者佈建工具來建立使用者和連絡人負載模擬。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="4f3b7-113">使用 Lync Server 壓力及效能工具套件安裝 Lync Server 使用者佈建工具。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="4f3b7-114">請確定已在前端伺服器或 Standard Edition server 上執行套件安裝程式 (CapacityPlanningTool.msi)。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="4f3b7-115">啟動 Lync Server 使用者佈建工具執行檔案 UserProvisioningTool.exe (位於 %installeddirectory%LyncStressAndPerfTool\\LyncStress) Standard Edition server 或前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4f3b7-116">您必須登入以 Domain Admins 安全性群組的成員才能執行 UserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="4f3b7-117">就必須執行從這個內容，因為 UserProvisioningTool.exe 會建立及設定新的 Active Directory 網域服務使用者。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4f3b7-118">當您建立大量的使用者 （10000 或多個） 時，請從高階電腦執行 UserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="4f3b7-119">請注意的網域控制站會也遇到高的負載時正在建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="4f3b7-120">為 Lync Server 使用者佈建工具開啟時，按一下 [**組態**]，然後選取 [**載入組態**。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="4f3b7-121">若要開始設定使用者和連絡人，載入封裝，SampleData.xml 中包含的預設檔案。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="4f3b7-122">這會預先填入範例資料，您需要為您的系統修訂的欄位。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="4f3b7-123">如果您有預先設定的 XML 檔案，其中已包含自訂的設定，請改為載入該檔案。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="4f3b7-124">下列各節所述的欄位中為 Lync Server 使用者佈建工具，填滿。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="4f3b7-125">![使用者建立] 索引標籤。](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "使用者建立] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="4f3b7-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="4f3b7-126">若要設定伺服器選項，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="4f3b7-127">在**前端集區 FQDN**] 中，輸入 Standard Edition server 或您想要用來主控使用者的前端集區的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="4f3b7-128">在 [**使用者名稱前置詞**，輸入您想要用來建立用於測試的使用者名稱的前置詞。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="4f3b7-129">在 [**密碼**] 中，指定將套用的所有測試使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="4f3b7-130">在**SIP 網域**中，輸入要用於測試使用者的 SIP Uri （統一資源識別元） 的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="4f3b7-131">在 [**帳戶網域**中，輸入您目前的 Active Directory 網域服務網域，您想要建立測試使用者所屬的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="4f3b7-132">在 [**組織單位**中，輸入您想要用來建立使用者物件 Active Directory 網域服務 OU 的名稱。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="4f3b7-133">如果 OU 不存在，則會加以建立。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="4f3b7-134">在 [**電話] 區域的程式碼**中，輸入將用於測試使用者帳戶的三位數區域程式碼。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="4f3b7-135">請確定該電話區碼不要與任何其他使用者的 Active Directory 網域服務中的區域代碼衝突。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="4f3b7-136">如果您想要測試為使用者啟用 Enterprise Voice，請選取 [**語音**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="4f3b7-137">在 [**使用者數量**，指定您想要建立的測試使用者的總數。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="4f3b7-138">在**開始的索引**中，指定要作為尾碼的使用者名稱前置詞的起始編號。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="4f3b7-139">建立使用者] 按鈕</span><span class="sxs-lookup"><span data-stu-id="4f3b7-139">Create Users Button</span></span>

<span data-ttu-id="4f3b7-140">當您按一下 [建立的使用者] 按鈕時，會驗證所有輸入的參數。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="4f3b7-141">如果有任何驗證錯誤，它會提示您若要修正這些輸入的值。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="4f3b7-142">如果所有輸入的值是否正確，則會啟動 Active Directory 網域服務中建立使用者。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="4f3b7-143">進度列會出現在此表單的底部。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="4f3b7-144">我們建議您不要關閉應用程式，當進度列作用中。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="4f3b7-145">使用者建立是緩慢的程序。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-145">User Creation is a slow process.</span></span> <span data-ttu-id="4f3b7-146">可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-146">It can take several minutes.</span></span> <span data-ttu-id="4f3b7-147">如果使用者數目很大，處理程序甚至可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="4f3b7-148">如果使用者已存在，他們會更新的任何變更。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="4f3b7-149">您可以驗證由以下列其中一個範圍中的使用者登入已建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="4f3b7-150">使用使用者的前置詞、 使用者數目和 @sipDomain 作為使用者名稱 (例如，LyncUser10@contoso.net)，以及指定的密碼。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="4f3b7-151">刪除使用者] 按鈕</span><span class="sxs-lookup"><span data-stu-id="4f3b7-151">Delete Users Button</span></span>

<span data-ttu-id="4f3b7-152">當您按一下刪除使用者] 按鈕上時，會驗證所有輸入的參數。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="4f3b7-153">如果有任何驗證錯誤，它會提示您若要修正這些輸入的值。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="4f3b7-154">如果所有輸入的值是否正確，則會啟動停用和刪除 Active Directory 網域服務中的使用者。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="4f3b7-155">進度列會出現在此表單的底部。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="4f3b7-156">我們建議您不要關閉應用程式，當進度列作用中。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="4f3b7-157">支援僅限美國格式的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="4f3b7-158">電話號碼一律會指派給使用者，以及 UserProvisioningTool.exe 所建立的所有使用者都啟用 Enterprise voice。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="4f3b7-159">任何使用的電話號碼，例如會議自動語音應答或 UC-PSTN 通話的案例使用此電話號碼正確地路由傳送來電。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="4f3b7-160">基於這個理由，每一位使用者必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="4f3b7-161">如果您有兩次建立使用者，命令將會失敗，除非您使用不同的區碼，或已停用舊的使用者使用<STRONG>Disable-csuser</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="4f3b7-162">建立連絡人之前，您必須先完成使用者複製，執行 [使用者] 索引標籤。如果您剛建立您的使用者，您必須等到 Lync Server 複寫完成，並填入資料庫中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="4f3b7-163">如果使用者尚未完成複寫，您會看到錯誤。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="4f3b7-164">您會知道當使用者完成複寫如果 Lync Server 2013 前端服務已啟動，或藉由成功，最後一個使用者執行<STRONG>Get-csuser</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="4f3b7-165">連絡人建立] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="4f3b7-165">Contacts Creation Tab</span></span>

<span data-ttu-id="4f3b7-166">[連絡人建立] 索引標籤可讓您指定的使用者的連絡人詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="4f3b7-167">![連絡人建立] 索引標籤。](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "連絡人建立] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="4f3b7-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="4f3b7-168">若要設定使用者的連絡人，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="4f3b7-169">在每位使用者的平均連絡人，指定要填入連絡人清單中的每位使用者的連絡人的平均數目。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="4f3b7-170">如果您想要建立數等於相同數目的每一位使用者的連絡人，請選取 [固定的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="4f3b7-171">如果您想要為使用者所建立的連絡人數目而異，清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="4f3b7-172">平均連絡人群組中每位使用者，指定每位使用者的連絡人群組的數目。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="4f3b7-173">此數字必須小於每位使用者的平均連絡人。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="4f3b7-174">在 [同盟 / 跨集區連絡人百分比，指定介於 0 到 100 之間的數字。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="4f3b7-175">此百分比的連絡人會建立與同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="4f3b7-176">在 [同盟 / 跨集區使用者前置詞，指定將會新增到本機使用者的連絡人清單的同盟使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="4f3b7-177">在 [同盟 / 跨集區的使用者 SIP 網域，請指定同盟使用者的 SIP 網域名稱。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f3b7-178">使用者都應該登入，當建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="4f3b7-179">在使用者建立] 索引標籤，確認參數正確無誤。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="4f3b7-180">使用者將會為其建立連絡人的範圍被取自使用者建立] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="4f3b7-181">按一下 [開始連絡人建立建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="4f3b7-182">此程序可能需要幾分鐘。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-182">This process can take several minutes.</span></span> <span data-ttu-id="4f3b7-183">它完成時，郵件時，會出現對話方塊之後 「 作業成功完成。 」</span><span class="sxs-lookup"><span data-stu-id="4f3b7-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="4f3b7-184">您可以驗證由使用者建立] 索引標籤所建立的使用者身分登入所建立的連絡人。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f3b7-185">建立連絡人之後，此工具會目標集區中重新啟動所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="4f3b7-186">根據多少連絡人所建立的這項作業可能需要較長 （最多 2 小時） 的開始，前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="4f3b7-187">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="4f3b7-187">Distribution List</span></span>

<span data-ttu-id="4f3b7-188">其中一項功能的 [Lync Server 2013 壓力及效能工具會模擬 Lync 2013 中的通訊清單 (DL) 的擴充功能。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="4f3b7-189">如果您不能在 UserProvisioningTool DL 擴充，您可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="4f3b7-190">![通訊群組清單的建立] 索引標籤。](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "通訊群組清單的建立] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="4f3b7-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="4f3b7-191">[通訊群組清單] 索引標籤可讓您建立的壓力及效能工具，將會用於通訊群組清單擴充功能的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="4f3b7-192">之前建立通訊群組清單，必須已安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="4f3b7-193">您必須執行 Lync Server 2013 ForestPrep。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="4f3b7-194">否則，DL 屬性不存在於 Active Directory 網域服務架構，此工具不能建立通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="4f3b7-195">若要設定通訊群組清單，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="4f3b7-196">在 [數字的通訊群組清單，指定您想要建立的通訊群組清單的總數。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="4f3b7-197">（建議使用開始的兩倍的使用者數目）。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="4f3b7-198">他們是從 0 到編號 n-1。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="4f3b7-199">在 [通訊群組清單的前置詞，指定通訊群組清單會有前置詞。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="4f3b7-200">例如 testDL0、 testDL1，等等，透過 testDL99，如果您指定 100 Dl 和 testDL 的前置詞，將名為通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="4f3b7-201">在最小 Dist.清單中的成員，指定要在每個通訊群組清單中新增使用者的數下限。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="4f3b7-202">在 [Dist.] 清單中的最大成員，指定要在每個通訊群組清單中新增使用者的數目上限。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="4f3b7-203">建立通訊群組清單] 按鈕</span><span class="sxs-lookup"><span data-stu-id="4f3b7-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="4f3b7-204">當您按一下 [建立通訊群組清單] 按鈕時，工具會查詢 Active Directory 網域服務，以查看是否通訊群組清單比對的首碼和號碼已經存在。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="4f3b7-205">此工具會建立不存在的探索。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="4f3b7-206">當將成員新增至新建立的通訊群組清單，它會選擇將使用者從使用者建立] 索引標籤上指定的範圍。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="4f3b7-207">位置資訊服務設定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="4f3b7-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="4f3b7-208">下列其中一個 [Lync Server 2013 壓力及效能工具的功能是產生虛設的設定檔的位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="4f3b7-209">位置資訊服務通常沒有任何明顯的效能影響的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="4f3b7-210">![位置資訊服務設定] 索引標籤。](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "位置資訊服務設定] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="4f3b7-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="4f3b7-211">如果您選擇來測試這項功能，您可以在表單中所述的值填滿，然後按一下 [產生 LIS 組態檔] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="4f3b7-212">它將會產生 CSV 檔案稱為 LIS\_Subnet.csv，LIS\_Switches.csv、 LIS\_Ports.csv 和 LIS\_WAP.csv。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="4f3b7-213">您可以再匯入這些 CSV 檔案 LIS 資料庫使用**組 CsLisSubnet**指令程式、**設定 CsLisSwitch**指令程式、**設定 CsLisPort** cmdlet 時及**組 CsWirelessAccessPoint** cmdlet 時，分別。</span><span class="sxs-lookup"><span data-stu-id="4f3b7-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

