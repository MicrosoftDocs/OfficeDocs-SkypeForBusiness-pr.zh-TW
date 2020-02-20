---
title: 設定使用者設定檔
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45d9c18045af3a3fba94070c5f1aa6e04f2b3fb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="6efb3-102">設定使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="6efb3-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6efb3-103">_**主題上次修改日期：** 2018年-10-11_</span><span class="sxs-lookup"><span data-stu-id="6efb3-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="6efb3-104">包含在 Lync Server 2013 壓力及效能工具套件的工具可讓您建立及設定您可以使用來執行負載模擬的測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6efb3-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="6efb3-105">使用 Lync Server 2013 使用者建立工具來建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="6efb3-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="6efb3-106">（如需詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)）。建立使用者之後，請使用 Lync Server 2013 負載組態工具設定使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="6efb3-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="6efb3-107">執行 Lync Server 2013 負載組態工具</span><span class="sxs-lookup"><span data-stu-id="6efb3-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="6efb3-108">若要設定使用者設定檔，請執行 Lync Server 2013 負載組態工具 (UserProfileGenerator.exe)，並填寫每個索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6efb3-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="6efb3-109">UserProfileGenerator.exe 會為每個您要執行模擬用戶端電腦產生的目錄。</span><span class="sxs-lookup"><span data-stu-id="6efb3-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="6efb3-110">每個用戶端目錄也隨附的指令碼，以啟動的 [Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe) 的所有執行個體。</span><span class="sxs-lookup"><span data-stu-id="6efb3-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6efb3-111">UserProfileGenerator 中指定之特定使用者的值必須符合集區的 Lync Server 2013 使用者建立工具 (UserProvisioningTool) 中所指定的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="6efb3-112">下列各節所述，請填寫的 Lync Server 2013 負載組態工具，每個索引標籤上的欄位。</span><span class="sxs-lookup"><span data-stu-id="6efb3-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="6efb3-113">常見的設定</span><span class="sxs-lookup"><span data-stu-id="6efb3-113">Common Configuration</span></span>

<span data-ttu-id="6efb3-114">Lync Server 2013 負載組態工具的 [**通用設定**] 索引標籤下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6efb3-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="6efb3-115">下列步驟所述填入 [**通用設定**] 索引標籤的欄位。</span><span class="sxs-lookup"><span data-stu-id="6efb3-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="6efb3-116">![一般設定] 索引標籤。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "一般設定] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="6efb3-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="6efb3-117">在**可用機器數目**，輸入或按一下您要用以執行 LyncPerfTool.exe 的電腦數目。</span><span class="sxs-lookup"><span data-stu-id="6efb3-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="6efb3-118">我們建議您擁有的每個 4500 的使用者，您將會模擬一部電腦。</span><span class="sxs-lookup"><span data-stu-id="6efb3-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="6efb3-119">如果您降低負載層級，或如果您使用可用的功能的子集，該數字可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="6efb3-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="6efb3-120">（**一般案例**] 索引標籤上所設定的載入層級）。</span><span class="sxs-lookup"><span data-stu-id="6efb3-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="6efb3-121">在 [**使用者名稱的前置字元**，輸入使用者的使用者名稱的前置詞。</span><span class="sxs-lookup"><span data-stu-id="6efb3-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="6efb3-122">若要登入，統一資源識別元 (URI) 將會是： UserPrefix\[使用者啟動索引...]（數字的使用者-1）\]@User 網域。</span><span class="sxs-lookup"><span data-stu-id="6efb3-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="6efb3-123">在**所有使用者的密碼**] 中，輸入已用來建立使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="6efb3-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="6efb3-124">如果您將此欄位保留空白，將會用的使用者名稱的密碼。</span><span class="sxs-lookup"><span data-stu-id="6efb3-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="6efb3-125">在**使用者開始的索引**中，按一下 [或輸入要設定第一位使用者的索引。</span><span class="sxs-lookup"><span data-stu-id="6efb3-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="6efb3-126">您可以設定不同範圍的不同類型或層級的負載，但您必須執行 UserProfileGenerator.exe 一次每個您想要設定的範圍。</span><span class="sxs-lookup"><span data-stu-id="6efb3-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="6efb3-127">在 [**使用者數量**] 中，按一下 [或輸入您要設定的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="6efb3-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="6efb3-128">在**使用者網域**中，輸入用於 SIP URI 的網域。</span><span class="sxs-lookup"><span data-stu-id="6efb3-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="6efb3-129">這用來建構的 SIP URI，每一位使用者登入 Lync Server 2013 前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="6efb3-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="6efb3-130">它可以是不同的帳戶網域。</span><span class="sxs-lookup"><span data-stu-id="6efb3-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="6efb3-131">在**帳戶網域**中，輸入登入 Active Directory 網域服務網域。</span><span class="sxs-lookup"><span data-stu-id="6efb3-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="6efb3-132">在**登中每秒 （每個執行個體）** 您想要的工具來登入的所有端點/使用者輸入並行端點的最大數目。</span><span class="sxs-lookup"><span data-stu-id="6efb3-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="6efb3-133">建議的速率是\<= 每秒/標準 SKU FE 2。</span><span class="sxs-lookup"><span data-stu-id="6efb3-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="6efb3-134">在**Access Proxy 或集區 FQDN]** 中，輸入您想用戶端連線至伺服器的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6efb3-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="6efb3-135">如果使用者從外部登入，指定 access proxy。</span><span class="sxs-lookup"><span data-stu-id="6efb3-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="6efb3-136">如果使用者是內部，指定其集區或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6efb3-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="6efb3-137">在 [**連接埠**，按一下或輸入您想讓使用者使用的 SIP 連接埠 （預設值為 5061）。</span><span class="sxs-lookup"><span data-stu-id="6efb3-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="6efb3-138">針對外部網路伺服器設定]，指定的**Access Proxy 或集區 FQDN**和**連接埠**。</span><span class="sxs-lookup"><span data-stu-id="6efb3-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="6efb3-139">這些設定僅用於外部端點負載模擬。</span><span class="sxs-lookup"><span data-stu-id="6efb3-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="6efb3-140">一般案例</span><span class="sxs-lookup"><span data-stu-id="6efb3-140">General Scenarios</span></span>

<span data-ttu-id="6efb3-141">Lync Server 2013 負載組態工具的 [**一般案例**] 索引標籤下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6efb3-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6efb3-142">設定每個您想要執行時，一般案例的載入層級和參數，或保留已停用。</span><span class="sxs-lookup"><span data-stu-id="6efb3-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="6efb3-143">![一般案例] 索引標籤。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "一般案例] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="6efb3-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="6efb3-144">在**立即訊息**，其中包括對等和會議，指定負載層級適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6efb3-145">負載層級 （除了位置資訊服務） 的所有欄位都有效值為<STRONG>已停用</STRONG>、 <STRONG>Low</STRONG>、 <STRONG>Medium</STRONG>、<STRONG>高</STRONG>，及<STRONG>自訂</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="6efb3-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="6efb3-146">選取低、 中、 高或自訂時，就會針對每種形式和用戶端產生組態。</span><span class="sxs-lookup"><span data-stu-id="6efb3-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="6efb3-147">高可能導致的最高的支援負載產生伺服器、 Medium 會對應至 60%的負載，及低會對應至 30%的負載。</span><span class="sxs-lookup"><span data-stu-id="6efb3-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="6efb3-148">**音訊會議**，也就是僅限音訊會議，在指定的載入層級適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6efb3-149">對等通話涵蓋在本主題稍後的語音案例一節。</span><span class="sxs-lookup"><span data-stu-id="6efb3-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="6efb3-150">若要啟用 MultiView，開啟該模式下的 [**進階**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6efb3-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="6efb3-151">在 [**應用程式共用**，指定的載入層級適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="6efb3-152">在 [**資料共同作業**，其中包含資料會議，指定的載入層級適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="6efb3-153">在 [**通訊群組清單擴充**，指定的載入層級適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6efb3-154">您必須也按一下 [**進階**] 按鈕，然後填入您的 Lync Server 使用者建立工具 (UserProvisioningTool.exe) 的**通訊群組清單**] 索引標籤設定相同值的欄位。</span><span class="sxs-lookup"><span data-stu-id="6efb3-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="6efb3-155">如需這些欄位的詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="6efb3-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="6efb3-156">在 [**通訊錄 Web 查詢**，也就是通訊錄查閱服務 （不檔案下載通訊錄），指定的載入層級適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6efb3-157">若要啟用通訊錄下載，請按一下對應的 [**進階**] 按鈕，然後將**EnableABSDownload**設為 true。</span><span class="sxs-lookup"><span data-stu-id="6efb3-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="6efb3-158">在 [**回應群組服務**中，指定的載入層級適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6efb3-159">您必須也按一下對應的 [**進階**] 按鈕，，，然後指定您已經建立佈建回應群組服務代理程式時的回應群組的 Uri。</span><span class="sxs-lookup"><span data-stu-id="6efb3-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="6efb3-160">您必須指定至少一個回應群組。</span><span class="sxs-lookup"><span data-stu-id="6efb3-160">You must specify at least one response group.</span></span> <span data-ttu-id="6efb3-161">您可以使用分號分隔多個回應群組。</span><span class="sxs-lookup"><span data-stu-id="6efb3-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="6efb3-162">RGSUriSuffixStartIndex 和 RGSUriSuffixEndIndex 更新的實際值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="6efb3-163">**位置資訊服務**] 中選取適當的值的載入層級。</span><span class="sxs-lookup"><span data-stu-id="6efb3-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="6efb3-164">位置資訊服務的載入層級必須**已啟用**] 或 [**已停用**。</span><span class="sxs-lookup"><span data-stu-id="6efb3-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6efb3-165">每個案例都位於，以及一組的核取方塊，啟用變化的案例旁邊的 [<STRONG>進階</STRONG>] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6efb3-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="6efb3-166"><STRONG>臨機操作</STRONG>表示要產生模擬的會議，將會建立整個小時。</span><span class="sxs-lookup"><span data-stu-id="6efb3-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="6efb3-167"><STRONG>大型 Conf</STRONG>表示將會模擬大型會議案例。</span><span class="sxs-lookup"><span data-stu-id="6efb3-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="6efb3-168"><STRONG>外部</STRONG>表示也模擬外部使用者。</span><span class="sxs-lookup"><span data-stu-id="6efb3-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="6efb3-169">這些按鈕及核取方塊，允許存取值專屬於每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並使自訂可能。</span><span class="sxs-lookup"><span data-stu-id="6efb3-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="6efb3-170">每個案例 （但不包括位置資訊服務） 的<STRONG>一般案例</STRONG>] 索引標籤上，如果負載層級的值是<STRONG>自訂</STRONG>]，然後交談率會進行計算在 [<STRONG>進階</STRONG>] 對話方塊中使用對應的欄位。</span><span class="sxs-lookup"><span data-stu-id="6efb3-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="6efb3-171">欄位名稱不同，根據案例，但將狀態欄位的描述，「 附註： 如果從下拉式清單功能表選取 [自訂，就只會使用此數字。 」</span><span class="sxs-lookup"><span data-stu-id="6efb3-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="6efb3-172">一般而言，<STRONG>高</STRONG>、<STRONG>中型</STRONG>與<STRONG>低</STRONG>的值會變更每種形式的所有案例的平衡使用者模型中內嵌的交談工資率。</span><span class="sxs-lookup"><span data-stu-id="6efb3-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="6efb3-173">如果沒有需要變更每種形式由於的差異在於預期的流量的負載層級，建議使用<STRONG>自訂</STRONG>交談工資率。</span><span class="sxs-lookup"><span data-stu-id="6efb3-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="6efb3-174">語音案例</span><span class="sxs-lookup"><span data-stu-id="6efb3-174">Voice Scenarios</span></span>

<span data-ttu-id="6efb3-175">Lync Server 2013 負載組態工具的 [**語音案例**] 索引標籤下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6efb3-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6efb3-176">使用 [**語音案例**] 索引標籤來設定的所有語音相關案例。</span><span class="sxs-lookup"><span data-stu-id="6efb3-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="6efb3-177">![語音案例] 索引標籤。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "語音案例] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="6efb3-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="6efb3-178">在**VoIP**時，按一下 [**進階**] 按鈕，，然後提供 [ **PhoneAreaCode**和**LocationProfile** （撥號對應表）] 欄位的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="6efb3-179">您也必須指定值的**載入層級**。</span><span class="sxs-lookup"><span data-stu-id="6efb3-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="6efb3-180">如果已啟用**VoIP**和**UC/PSTN 閘道**的載入層級，然後就一定會產生公用交換的電話網路 (PSTN) 整合的通訊 (UC) 組態檔，將會模擬外部通話。</span><span class="sxs-lookup"><span data-stu-id="6efb3-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="6efb3-181">**UC/PSTN 閘道**] 中指定的載入層級的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="6efb3-182">如果您選取的載入層級以外的**已停用**，您必須提供**PSTN 區域**代碼值中繼伺服器與 PSTN] 底下按一下 [**新增**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6efb3-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="6efb3-183">確認您已設定該區域代碼的路由。</span><span class="sxs-lookup"><span data-stu-id="6efb3-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6efb3-184">若要確認語音路由組態，您可以使用 [Lync Server Control Panel] 或 [Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="6efb3-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="6efb3-185">在 [**會議服務員**，指定的載入層級的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="6efb3-186">選取的載入層級 （以外的連接**已停用**)，將啟用 [**電話號碼**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6efb3-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="6efb3-187">輸入您想要使用自動語音應答的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6efb3-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="6efb3-188">此外，按一下 [**進階**] 按鈕，然後指定**LocationProfile**欄位的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="6efb3-189">在 [**通話駐留服務**中，指定**的載入層級**適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="6efb3-190">在**中繼伺服器和 PSTN**，每個中繼伺服器，您想要使用，您必須個別的 PSTN 模擬器。</span><span class="sxs-lookup"><span data-stu-id="6efb3-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="6efb3-191">您已決定您要做為模擬器用戶端之後，您需要在您設定的 PSTN 模擬器連接埠上設定中繼伺服器，以將通話路由傳送至該電腦。</span><span class="sxs-lookup"><span data-stu-id="6efb3-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="6efb3-192">按一下 [**新增]** 來為中繼伺服器設定的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6efb3-193">每個案例都位於其旁邊的 [<STRONG>進階</STRONG>] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6efb3-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6efb3-194">這些按鈕可讓每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並啟用自訂的特定值的存取。</span><span class="sxs-lookup"><span data-stu-id="6efb3-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6efb3-195"><STRONG>語音案例</STRONG>] 索引標籤上每個案例中，如果<STRONG>負載層級</STRONG>的值是<STRONG>自訂</STRONG>]，然後交談率會進行計算使用 [<STRONG>進階</STRONG>] 對話方塊中的對應的欄位。</span><span class="sxs-lookup"><span data-stu-id="6efb3-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="6efb3-196">欄位名稱不同，根據案例，但將狀態欄位的描述，「 附註： 如果從下拉式清單功能表選取 [自訂，就只會使用此數字。 」</span><span class="sxs-lookup"><span data-stu-id="6efb3-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="6efb3-197">到達</span><span class="sxs-lookup"><span data-stu-id="6efb3-197">Reach</span></span>

<span data-ttu-id="6efb3-198">範圍是支援透過前端伺服器安裝 Unified Communications Web API (UCWA) 伺服器的會議案例的 Lync Server 2013 中新的體驗。</span><span class="sxs-lookup"><span data-stu-id="6efb3-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="6efb3-199">Lync Server 2013 負載組態工具的 [**連線到**] 索引標籤下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6efb3-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6efb3-200">使用 [**連線到**] 索引標籤來設定所有範圍相關的案例。</span><span class="sxs-lookup"><span data-stu-id="6efb3-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="6efb3-201">![達到] 索引標籤。](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "達到] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="6efb3-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="6efb3-202">按一下 [**一般到達設定**] 旁的 [**進階**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6efb3-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="6efb3-203">Set 功能變數**UcwaTargetServerUrl**至 Director 集區虛擬 IP (VIP) 或前端集區 VIP。</span><span class="sxs-lookup"><span data-stu-id="6efb3-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="6efb3-204">在**應用程式共用**、**資料共同作業**，以及**IM**，選取適當的值的**載入層級**。</span><span class="sxs-lookup"><span data-stu-id="6efb3-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6efb3-205">每個案例都位於其旁邊的 [<STRONG>進階</STRONG>] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6efb3-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6efb3-206">這些按鈕可讓每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並啟用自訂的特定值的存取。</span><span class="sxs-lookup"><span data-stu-id="6efb3-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6efb3-207">針對每個範圍案例，如果<STRONG>負載層級</STRONG>是<STRONG>自訂</STRONG>]，然後<STRONG>ConversationsPerHour</STRONG>欄位中指定的值是用來取代預設值</span><span class="sxs-lookup"><span data-stu-id="6efb3-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="6efb3-208">若要設定的所有 mobility 相關案例中使用 [**行動性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6efb3-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="6efb3-209">![行動性] 索引標籤。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "行動性] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="6efb3-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="6efb3-210">按一下 [**進階**] 按鈕旁**行動力 (UCWA)**。</span><span class="sxs-lookup"><span data-stu-id="6efb3-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="6efb3-211">Set 功能變數**UcwaTargetServerUrl**至 Director 集區虛擬 IP (VIP) 或前端集區 VIP。</span><span class="sxs-lookup"><span data-stu-id="6efb3-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="6efb3-212">在**Presence and P2P Instant Messaging\\音訊**，選取要啟用行動性案例模擬**的載入層級**適當的值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6efb3-213">每個案例都位於其旁邊的 [<STRONG>進階</STRONG>] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6efb3-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6efb3-214">這些按鈕可讓每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並啟用自訂的特定值的存取。</span><span class="sxs-lookup"><span data-stu-id="6efb3-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6efb3-215">針對每個範圍案例中，如果<STRONG>負載層級</STRONG><STRONG>自訂</STRONG>]，然後<STRONG>ConversationsPerHour</STRONG>欄位中指定的值使用而不是預設值。</span><span class="sxs-lookup"><span data-stu-id="6efb3-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="6efb3-216">摘要</span><span class="sxs-lookup"><span data-stu-id="6efb3-216">Summary</span></span>

<span data-ttu-id="6efb3-217">Lync Server 2013 負載組態工具的 [**摘要**] 索引標籤下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6efb3-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6efb3-218">![摘要] 索引標籤。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "摘要] 索引標籤。")</span><span class="sxs-lookup"><span data-stu-id="6efb3-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="6efb3-219">[**摘要**] 索引標籤會指出哪些使用者可使用每個案例。</span><span class="sxs-lookup"><span data-stu-id="6efb3-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="6efb3-220">它是可以手動設定使用者的號碼範圍依選取**啟用自訂使用者範圍產生**] 核取方塊，再連按兩下 [您想要自訂的**使用者範圍**的表格中的案例。</span><span class="sxs-lookup"><span data-stu-id="6efb3-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="6efb3-221">當啟動時，才能在對應的登入速度產生批次檔案中包含的延遲，請檢查 (RunClient.bat) 新增登入的延遲。</span><span class="sxs-lookup"><span data-stu-id="6efb3-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="6efb3-222">這很有用，避免伺服器超載時登入大量的使用者。</span><span class="sxs-lookup"><span data-stu-id="6efb3-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="6efb3-223">按一下 [**產生的檔案**，然後選取您想要用來產生組態的資料夾。</span><span class="sxs-lookup"><span data-stu-id="6efb3-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="6efb3-224">成功建立您的檔案時，會出現類似下列的圖] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6efb3-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="6efb3-225">![檔案已建立的認可。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "檔案已建立的認可。")</span><span class="sxs-lookup"><span data-stu-id="6efb3-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6efb3-226">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6efb3-226">See Also</span></span>


[<span data-ttu-id="6efb3-227">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="6efb3-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
