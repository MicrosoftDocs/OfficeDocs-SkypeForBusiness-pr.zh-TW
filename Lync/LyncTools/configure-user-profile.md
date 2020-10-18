---
title: 設定使用者設定檔
description: 設定使用者設定檔。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573089"
---
# <a name="configure-user-profile"></a><span data-ttu-id="231aa-103">設定使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="231aa-103">Configure User Profile</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="231aa-104">_**主題上次修改日期：** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="231aa-104">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="231aa-105">Lync Server 2013 應力和效能工具套件所包含的工具可讓您建立及設定測試使用者帳戶，以供您用來執行負載模擬。</span><span class="sxs-lookup"><span data-stu-id="231aa-105">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="231aa-106">使用 Lync Server 2013 使用者建立工具來建立使用者。</span><span class="sxs-lookup"><span data-stu-id="231aa-106">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="231aa-107"> (如需詳細資訊，請參閱 [建立使用者和連絡人](create-users-and-contacts.md)。 ) 建立使用者之後，使用 Lync Server 2013 負載設定工具設定使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="231aa-107">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="231aa-108">執行 Lync Server 2013 載入設定工具</span><span class="sxs-lookup"><span data-stu-id="231aa-108">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="231aa-109">若要設定使用者設定檔，請執行 Lync Server 2013 載入設定工具 ( # A0) 並填妥每個索引標籤。</span><span class="sxs-lookup"><span data-stu-id="231aa-109">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="231aa-110">UserProfileGenerator.exe 會為您需要執行模擬的每一部用戶端電腦產生目錄。</span><span class="sxs-lookup"><span data-stu-id="231aa-110">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="231aa-111">每個用戶端目錄也附帶一個腳本，以啟動 Lync Server 2013 應力和效能工具 ( # A0) 的所有實例。</span><span class="sxs-lookup"><span data-stu-id="231aa-111">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="231aa-112">Userprofilegenerator.exe 中指定的使用者特定值，必須符合 Lync Server 2013 使用者建立工具中所指定的值，才能 (集區的 UserProvisioningTool) 。</span><span class="sxs-lookup"><span data-stu-id="231aa-112">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="231aa-113">在 [Lync Server 2013 載入設定工具] 的每個索引標籤上填入欄位，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="231aa-113">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="231aa-114">一般設定</span><span class="sxs-lookup"><span data-stu-id="231aa-114">Common Configuration</span></span>

<span data-ttu-id="231aa-115">下圖顯示 Lync Server 2013 Load Configuration 工具的 [ **一般** 設定] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="231aa-115">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="231aa-116">填寫 [ **一般** 設定] 索引標籤的欄位，如下列步驟所述。</span><span class="sxs-lookup"><span data-stu-id="231aa-116">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="231aa-117">![通用設定] 索引標籤。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "通用設定] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="231aa-117">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="231aa-118">在 [ **可用機器數目**] 中，輸入或按一下您要用來執行 LyncPerfTool.exe 的電腦數目。</span><span class="sxs-lookup"><span data-stu-id="231aa-118">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="231aa-119">建議您為每個要模擬的4500使用者提供一部電腦。</span><span class="sxs-lookup"><span data-stu-id="231aa-119">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="231aa-120">如果您降低負載層級，或僅使用可用功能的子集，該數位可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="231aa-120">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="231aa-121"> (負載層級是在 [ **一般案例** ] 索引標籤上設定。 ) </span><span class="sxs-lookup"><span data-stu-id="231aa-121">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="231aa-122">在 [ **使用者名稱的前置**詞] 中，輸入使用者之使用者名稱的前置詞。</span><span class="sxs-lookup"><span data-stu-id="231aa-122">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="231aa-123">若要登入，統一資源識別項 (URI) 會是： UserPrefix \[ User Start Index ... (使用者數目-1) \] @User Domain。</span><span class="sxs-lookup"><span data-stu-id="231aa-123">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="231aa-124">在 [ **所有使用者的密碼**] 中，輸入用來建立使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="231aa-124">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="231aa-125">如果您將此欄位保留空白，則會將使用者名稱當作密碼使用。</span><span class="sxs-lookup"><span data-stu-id="231aa-125">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="231aa-126">在 [ **使用者起始索引**] 中，按一下或輸入要設定之第一個使用者的索引。</span><span class="sxs-lookup"><span data-stu-id="231aa-126">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="231aa-127">您可以為不同的類型或不同的負載層級設定不同的範圍，但是必須針對您要設定的範圍執行 UserProfileGenerator.exe 一次。</span><span class="sxs-lookup"><span data-stu-id="231aa-127">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="231aa-128">在 [ **使用者數目**] 中，按一下或輸入您要設定的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="231aa-128">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="231aa-129">在 [ **使用者網域**] 中，輸入用於 SIP URI 的網域。</span><span class="sxs-lookup"><span data-stu-id="231aa-129">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="231aa-130">這是用來建立每一位使用者的 SIP URI，以登入 Lync Server 2013 前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="231aa-130">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="231aa-131">它可以不同于帳戶網域。</span><span class="sxs-lookup"><span data-stu-id="231aa-131">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="231aa-132">在 [ **帳戶網域**] 中，輸入 Active Directory 網域服務網域登入。</span><span class="sxs-lookup"><span data-stu-id="231aa-132">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="231aa-133">輸入您想要讓工具在所有端點/使用者中登入的每 \*\*秒以每秒 (每個實例) \*\* 的並行端點數目上限。</span><span class="sxs-lookup"><span data-stu-id="231aa-133">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="231aa-134">建議的速率為 \< = 每秒 2/STANDARD SKU FE。</span><span class="sxs-lookup"><span data-stu-id="231aa-134">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="231aa-135">在 [ **Access Proxy 或集區 FQDN**] 中，輸入您要讓用戶端連接之伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="231aa-135">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="231aa-136">若使用者在外部登入，請指定 access proxy。</span><span class="sxs-lookup"><span data-stu-id="231aa-136">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="231aa-137">如果使用者是內部使用者，請指定其集區或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="231aa-137">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="231aa-138">在 [ **埠**] 中，按一下或輸入您想要讓使用者用於 SIP 的埠 (預設值為 5061) 。</span><span class="sxs-lookup"><span data-stu-id="231aa-138">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="231aa-139">針對 [外部網路伺服器設定]，指定 **Access Proxy 或集區 FQDN** 和 **埠**。</span><span class="sxs-lookup"><span data-stu-id="231aa-139">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="231aa-140">這些設定只用于外部端點的負載模擬。</span><span class="sxs-lookup"><span data-stu-id="231aa-140">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="231aa-141">一般案例</span><span class="sxs-lookup"><span data-stu-id="231aa-141">General Scenarios</span></span>

<span data-ttu-id="231aa-142">[Lync Server 2013 載入設定工具] 的 **[一般案例** ] 索引標籤如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="231aa-142">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="231aa-143">針對您想要執行的每個一般案例，設定負載層級和參數，或停用停用。</span><span class="sxs-lookup"><span data-stu-id="231aa-143">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="231aa-144">![一般案例] 索引標籤。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "一般案例] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="231aa-144">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="231aa-145">在 **立即訊息**中（包括對等和會議），為負載層級指定適當的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-145">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="231aa-146">所有欄位的負載層級值 (，但位置資訊服務) 會 <STRONG>停用</STRONG>、 <STRONG>低</STRONG>、 <STRONG>中</STRONG>、 <STRONG>高</STRONG>及 <STRONG>自訂</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="231aa-146">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="231aa-147">選取 [低]、[中]、[高] 或 [自訂] 時，將會針對每個模態和用戶端產生設定。</span><span class="sxs-lookup"><span data-stu-id="231aa-147">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="231aa-148">High 會產生為伺服器產生的最大支援負載，中會對應至60% 的負載，低的負載會對應至30% 的負載。</span><span class="sxs-lookup"><span data-stu-id="231aa-148">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="231aa-149">在 [ **音訊會議**] （僅限音訊會議）中，為 [負載層級] 指定適當的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-149">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="231aa-150">對等通話會在本主題稍後的語音案例區段中講述。</span><span class="sxs-lookup"><span data-stu-id="231aa-150">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="231aa-151">若要啟用所有的查看，請開啟該形式的 [ **高級** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="231aa-151">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="231aa-152">在 [ **應用程式共用**] 中，為 [負載層級] 指定適當的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-152">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="231aa-153">在 [ **資料**共同作業] （包含資料會議）中，為 [負載層級] 指定適當的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-153">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="231aa-154">在 [ **通訊群組清單展開**] 中，為 [負載層級] 指定適當的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-154">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="231aa-155">您也必須按一下 [ **高級** ] 按鈕，然後以 Lync Server 使用者建立工具 ( # A0) 中的 [ **通訊群組清單** ] 索引標籤上所設定的相同值填入欄位。</span><span class="sxs-lookup"><span data-stu-id="231aa-155">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="231aa-156">如需這些欄位的詳細資訊，請參閱 [建立使用者和連絡人](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="231aa-156">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="231aa-157">在 [通訊 **簿 Web 查詢**] 中，這是通訊錄的查閱服務 (不是通訊錄檔案下載) ，請為 [負載層級] 指定適當的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-157">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="231aa-158">若要啟用通訊錄下載，請按一下對應的 [ **高級** ] 按鈕，然後將 **EnableABSDownload** 設定為 true。</span><span class="sxs-lookup"><span data-stu-id="231aa-158">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="231aa-159">在 [ **回應群組服務**] 中，指定適當的負載層級值。</span><span class="sxs-lookup"><span data-stu-id="231aa-159">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="231aa-160">您也必須按一下對應的 [ **高級** ] 按鈕，然後指定在布建回應群組服務代理程式時，您已建立的回應群組 URIs。</span><span class="sxs-lookup"><span data-stu-id="231aa-160">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="231aa-161">您必須指定至少一個回應群組。</span><span class="sxs-lookup"><span data-stu-id="231aa-161">You must specify at least one response group.</span></span> <span data-ttu-id="231aa-162">使用分號分隔多個回應群組。</span><span class="sxs-lookup"><span data-stu-id="231aa-162">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="231aa-163">將 RGSUriSuffixStartIndex 及 RGSUriSuffixEndIndex 更新為實際值。</span><span class="sxs-lookup"><span data-stu-id="231aa-163">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="231aa-164">在 [ **位置資訊服務**] 中，選取適當的負載層級值。</span><span class="sxs-lookup"><span data-stu-id="231aa-164">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="231aa-165">必須 **啟用** 或 **停用**位置資訊服務的負載層級。</span><span class="sxs-lookup"><span data-stu-id="231aa-165">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="231aa-166">每個案例旁都有一個「 <STRONG>高級</STRONG> 」按鈕，以及一組啟用案例變化的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="231aa-166">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="231aa-167"><STRONG>特別表示要</STRONG> 產生一小時內建立的會議類比。</span><span class="sxs-lookup"><span data-stu-id="231aa-167"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="231aa-168">「<STRONG>大型</STRONG>會議」表示將會模擬大型會議案例。</span><span class="sxs-lookup"><span data-stu-id="231aa-168"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="231aa-169"><STRONG>外部</STRONG> 方式也可模擬外部使用者。</span><span class="sxs-lookup"><span data-stu-id="231aa-169"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="231aa-170">這些按鈕和核取方塊可讓您存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 的行為，並可進行自訂。</span><span class="sxs-lookup"><span data-stu-id="231aa-170">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="231aa-171">針對 [ <STRONG>一般案例</STRONG> ] 索引標籤上的每個案例 (除位置資訊服務) 之外，如果負載層級的值是 [ <STRONG>自訂</STRONG>]，就會使用 [ <STRONG>高級</STRONG> ] 對話方塊中對應的欄位來計算交談率。</span><span class="sxs-lookup"><span data-stu-id="231aa-171">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="231aa-172">功能變數名稱會不同，具體取決於案例，但是欄位描述將會是「注意：只有從下拉式功能表中選取 [自訂] 時，才會使用此號碼。</span><span class="sxs-lookup"><span data-stu-id="231aa-172">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="231aa-173">一般說來， <STRONG>高</STRONG>、 <STRONG>中</STRONG>、 <STRONG>低</STRONG> 的值將會以所有案例的平衡的使用者模型來變更每個形式的交談比率。</span><span class="sxs-lookup"><span data-stu-id="231aa-173">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="231aa-174">如果因預期的使用量差異而需要變更每個模態的負載層級，建議使用 <STRONG>自訂</STRONG> 交談率。</span><span class="sxs-lookup"><span data-stu-id="231aa-174">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="231aa-175">語音案例</span><span class="sxs-lookup"><span data-stu-id="231aa-175">Voice Scenarios</span></span>

<span data-ttu-id="231aa-176">[Lync Server 2013 載入設定工具] 的 [ **語音案例** ] 索引標籤如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="231aa-176">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="231aa-177">使用 [ **語音案例** ] 索引標籤來設定所有語音相關案例。</span><span class="sxs-lookup"><span data-stu-id="231aa-177">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="231aa-178">![語音案例] 索引標籤。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "語音案例] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="231aa-178">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="231aa-179">在 **VoIP**中，按一下 [ **高級** ] 按鈕，然後提供 **PhoneAreaCode** 和 **microsoft.rtc.management.writableconfig.policy.voice.locationprofile** (撥號對應表) ] 欄位的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-179">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="231aa-180">您也必須指定 **負載層級**的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-180">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="231aa-181">如果啟用 **VoIP** 和 **UC/PSTN 閘道** 的負載層級，則會永遠會產生一部公用交換電話網路 (PSTN) 至整合通訊 (UC) 設定檔，以模擬外部通話。</span><span class="sxs-lookup"><span data-stu-id="231aa-181">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="231aa-182">在 [ **UC/PSTN 閘道**] 中，為 [負載層級] 指定一個值。</span><span class="sxs-lookup"><span data-stu-id="231aa-182">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="231aa-183">如果您選取**停用**以外的載入層級，您必須按一下 [轉送伺服器和 PSTN] 底下的 [**新增**] 按鈕，為**PSTN 區域碼**提供值。</span><span class="sxs-lookup"><span data-stu-id="231aa-183">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="231aa-184">請確認您是否已為該區號設定路由。</span><span class="sxs-lookup"><span data-stu-id="231aa-184">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="231aa-185">您可以使用 Lync Server 控制台或 Lync Server 管理命令介面來驗證語音路由設定。</span><span class="sxs-lookup"><span data-stu-id="231aa-185">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="231aa-186">在 **會議助理**中，指定負載層級的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-186">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="231aa-187">選取除 **停用**) 以外的負載層級 (會啟用 [ **電話號碼** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="231aa-187">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="231aa-188">輸入您要使用之自動語音應答的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="231aa-188">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="231aa-189">此外，按一下 [ **高級** ] 按鈕，然後指定 [ **microsoft.rtc.management.writableconfig.policy.voice.locationprofile** ] 欄位的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-189">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="231aa-190">在 [ **通話駐留服務**] 中，為 [ **負載層級**] 指定適當的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-190">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="231aa-191">在中繼 **伺服器和 PSTN**中，針對您想要使用的每個轉送伺服器，您必須有個別的 PSTN 模擬器。</span><span class="sxs-lookup"><span data-stu-id="231aa-191">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="231aa-192">決定要用來做為模擬器的用戶端後，您需要將您的轉送伺服器設定為在您設定的 PSTN 模擬器埠上，將通話路由傳送至該電腦。</span><span class="sxs-lookup"><span data-stu-id="231aa-192">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="231aa-193">按一下 [ **新增** ] 以設定轉送伺服器的值。</span><span class="sxs-lookup"><span data-stu-id="231aa-193">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="231aa-194">每個案例都有一個位於它旁邊的 [ <STRONG>高級</STRONG> ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="231aa-194">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="231aa-195">這些按鈕允許存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 並啟用自訂的行為。</span><span class="sxs-lookup"><span data-stu-id="231aa-195">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="231aa-196">在 [ <STRONG>語音案例</STRONG> ] 索引標籤上的每個案例中，如果 [ <STRONG>負載層級</STRONG> ] 的值為 [ <STRONG>自訂</STRONG>]，則會使用 [ <STRONG>高級</STRONG> ] 對話方塊中對應的欄位來計算交談率。</span><span class="sxs-lookup"><span data-stu-id="231aa-196">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="231aa-197">功能變數名稱會不同，具體取決於案例，但是欄位描述將會是「注意：只有從下拉式功能表中選取 [自訂] 時，才會使用此號碼。</span><span class="sxs-lookup"><span data-stu-id="231aa-197">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="231aa-198">達到</span><span class="sxs-lookup"><span data-stu-id="231aa-198">Reach</span></span>

<span data-ttu-id="231aa-199">「接觸」是 Lync Server 2013 中的新經驗，可透過 Front-End Server 上安裝的整合通訊 Web API (UCWA) 伺服器來支援會議案例。</span><span class="sxs-lookup"><span data-stu-id="231aa-199">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="231aa-200">下圖顯示 Lync Server 2013 負載設定工具的 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="231aa-200">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="231aa-201">使用 [ **範圍** ] 索引標籤來設定所有與範圍相關的案例。</span><span class="sxs-lookup"><span data-stu-id="231aa-201">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="231aa-202">![[接觸] 索引標籤。](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "[接觸] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="231aa-202">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="231aa-203">按一下 [**一般到達設定**] 旁的 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="231aa-203">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="231aa-204">將欄位 **UcwaTargetServerUrl** 為 Director 集區虛擬 IP (VIP) 或前端集區 VIP。</span><span class="sxs-lookup"><span data-stu-id="231aa-204">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="231aa-205">在 [ **應用程式共用**]、[ **資料**共同作業] 和 [ **IM**] 中，選取適當的 **負載層級**值。</span><span class="sxs-lookup"><span data-stu-id="231aa-205">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="231aa-206">每個案例都有一個位於它旁邊的 [ <STRONG>高級</STRONG> ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="231aa-206">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="231aa-207">這些按鈕允許存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 並啟用自訂的行為。</span><span class="sxs-lookup"><span data-stu-id="231aa-207">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="231aa-208">針對每個接觸案例，如果 <STRONG>負載層級</STRONG> 為 [ <STRONG>自訂</STRONG>]，則使用 <STRONG>ConversationsPerHour</STRONG> 欄位中指定的值，而不是預設值</span><span class="sxs-lookup"><span data-stu-id="231aa-208">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="231aa-209">使用 [ **行動性** ] 索引標籤來設定所有行動相關案例。</span><span class="sxs-lookup"><span data-stu-id="231aa-209">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="231aa-210">![行動] 索引標籤。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "行動] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="231aa-210">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="231aa-211">按一下 [**行動性 (UCWA) **旁的 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="231aa-211">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="231aa-212">將欄位 **UcwaTargetServerUrl** 為 Director 集區虛擬 IP (VIP) 或前端集區 VIP。</span><span class="sxs-lookup"><span data-stu-id="231aa-212">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="231aa-213">在 [ **顯示並 P2P 立即訊息 \\ 音訊**] 中，選取適當的 **負載層級** 值，以啟用行動案例類比。</span><span class="sxs-lookup"><span data-stu-id="231aa-213">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="231aa-214">每個案例都有一個位於它旁邊的 [ <STRONG>高級</STRONG> ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="231aa-214">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="231aa-215">這些按鈕允許存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 並啟用自訂的行為。</span><span class="sxs-lookup"><span data-stu-id="231aa-215">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="231aa-216">針對每個接觸案例，如果 <STRONG>負載層級</STRONG> 為 [ <STRONG>自訂</STRONG>]，則使用 <STRONG>ConversationsPerHour</STRONG> 欄位中指定的值，而不是預設值。</span><span class="sxs-lookup"><span data-stu-id="231aa-216">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="231aa-217">摘要</span><span class="sxs-lookup"><span data-stu-id="231aa-217">Summary</span></span>

<span data-ttu-id="231aa-218">下圖顯示 Lync Server 2013 Load Configuration 工具的 [ **摘要** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="231aa-218">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="231aa-219">![摘要] 索引標籤。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "摘要] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="231aa-219">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="231aa-220">[ **摘要** ] 索引標籤會指出要針對每個案例使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="231aa-220">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="231aa-221">您可以手動設定使用者號碼範圍，方法是選取 [ **啟用自訂使用者範圍產生** ] 核取方塊，然後在具有您要自訂之 **使用者範圍** 的資料表中按兩下案例。</span><span class="sxs-lookup"><span data-stu-id="231aa-221">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="231aa-222">檢查 ( # A0) 在啟動時加入登入延遲，以便在產生的批次處理檔案中包含延遲，以對應于登入率。</span><span class="sxs-lookup"><span data-stu-id="231aa-222">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="231aa-223">當您簽署大量使用者時，這是避免伺服器超載的有用方法。</span><span class="sxs-lookup"><span data-stu-id="231aa-223">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="231aa-224">按一下 [ **產生**檔案]，然後選取您要產生設定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="231aa-224">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="231aa-225">當您已成功建立檔案時，就會出現類似下圖的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="231aa-225">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="231aa-226">![確認已建立檔案。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "確認已建立檔案。")</span><span class="sxs-lookup"><span data-stu-id="231aa-226">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="231aa-227">另請參閱</span><span class="sxs-lookup"><span data-stu-id="231aa-227">See Also</span></span>


[<span data-ttu-id="231aa-228">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="231aa-228">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
