---
title: Lync Server 2013：將 Lync Server 2013 設定為使用 Microsoft Exchange Server 上的整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b297a505b1a12335e545895e0203ffc0e29c7354
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507630"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="0d7a4-102">設定 Lync Server 2013，以搭配 Microsoft Exchange Server 上的整合通訊使用</span><span class="sxs-lookup"><span data-stu-id="0d7a4-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="0d7a4-103">_**主題上次修改日期：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="0d7a4-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="0d7a4-104">這個步驟需要 Exchange UM 整合公用程式 (OcsUmUtil.exe)。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="0d7a4-105">此工具位於中的 Lync Server 2013 伺服器上。 \\Program Files \\ 常見檔案 \\ Microsoft Lync Server 2013 \\ 支援資料夾。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="0d7a4-106">執行 Exchange UM 整合公用程式</span><span class="sxs-lookup"><span data-stu-id="0d7a4-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="0d7a4-107">Exchange UM 整合公用程式必須從具有下列特性的使用者帳戶執行：</span><span class="sxs-lookup"><span data-stu-id="0d7a4-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="0d7a4-108">RTCUniversalServerAdmins 與 RtcUniversalUserAdmins 群組的成員資格 (包括讀取 Exchange Server Unified Messaging 設定的權限)。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="0d7a4-109">網域內的使用者權限，可在指定的組織單位 (OU) 容器中建立連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="0d7a4-110">當您執行 Exchange UM 整合公用程式時，它會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="0d7a4-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="0d7a4-111">針對 Enterprise Voice 使用者所要使用的每一個自動語音應答和訂戶存取號碼來建立連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="0d7a4-112">驗證每個 Enterprise Voice 撥號對應表的名稱是否符合其對應的整合通訊 (UM) 撥號對應表電話內容。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="0d7a4-113">只有當 UM 撥號對應表在 exchange 2010 Service Pack 1 (SP1) 上的 *exchange 版本* 上執行時，才需要這種對應。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d7a4-114">在執行 Exchange UM 整合公用程式之前，請確定您已完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="0d7a4-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="0d7a4-115">如 Exchange 產品檔中所述，建立一或多個 Exchange UM 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="0d7a4-116">如需 Microsoft Exchange Server 2010，請參閱 &quot; Create a UM 撥號對應表 &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> 。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="0d7a4-117">如需 Microsoft Exchange Server 2007 Service Pack 1 (SP1) ，請參閱 how &quot; To Create a 整合通訊 SIP URI 撥號對應表， &quot; 網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> 。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="0d7a4-118">建立一或多個對應的 Lync Server 撥號對應表，如在 <a href="lync-server-2013-create-a-dial-plan.md">Lync Server 2013 中建立撥號</a>對應表所述。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="0d7a4-119">如果您使用的是舊于 Microsoft Exchange Server 2010 SP1 版本的 Exchange，則必須在 [Lync Server 2013 撥號對應表 <STRONG>簡易名稱</STRONG> ] 欄位中輸入對應 Exchange 整合通訊 (UM) SIP 撥號對應表的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="0d7a4-120">如果您使用的是 Microsoft Exchange Server 2010 SP1 或最新的 service pack，則不需要此撥號對應表名稱比對。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="0d7a4-121">請建立一個自動語音應答，並且確定訂戶存取號碼和自動語音應答號碼的格式都是 E.164。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="0d7a4-122">若要執行 Exchange UM 整合公用程式</span><span class="sxs-lookup"><span data-stu-id="0d7a4-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="0d7a4-123">在前端伺服器上，開啟命令提示字元，並輸入 **cd%CommonProgramFiles% \\ Microsoft Lync Server 2013 \\ 支援**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="0d7a4-124">輸入 **OcsUmUtil.exe**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="0d7a4-125">按一下 **[載入資料]** 以找出所有受信任的 Exchange 樹系。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="0d7a4-126">在 **[SIP 撥號對應表]** 清單中，選取您要為它建立連絡人物件的 UM SIP 撥號對應表，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="0d7a4-p104">在 **[連絡人]** 方塊中，接受預設的組織單位，或按一下 **[瀏覽]** 來啟動 **[OU 選擇器]**。在 **[OU 選擇器]** 方塊中，您可以選擇一個 OU，再按一下 **[確定]**，或者您可以按一下 **[建立新的 OU]**，在根目錄底下或網域中其他任何 OU 底下建立新的組織單位 (例如，"OU=RTC Special Accounts,DC=fourthcoffee,DC=com")，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d7a4-129">您所選取或建立之 OU 的辨別名稱 (DN)，現在會在 <STRONG>[組織單位]</STRONG> 方塊中顯示。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="0d7a4-130">在 **[名稱]** 方塊中，接受預設的撥號對應表名稱，或者為您要建立的連絡人物件輸入新的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d7a4-131">例如，如果您要建立訂閱者存取連絡人物件，可以直接命名為「訂閱者存取」。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="0d7a4-132">在 **[SIP 位址]** 方塊中，接受預設 SIP 位址或輸入新的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d7a4-133">如果輸入新的 SIP 位址，必須以 <STRONG>SIP:</STRONG> 開頭 (也就是 "SIP:"，包括冒號)。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="0d7a4-134">在 [ **伺服器或集** 區] 清單中，選取要啟用連絡人物件的 Standard Edition 伺服器或前端集區。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d7a4-135">您選取的集區最好是與啟用 Enterprise Voice 與 Exchange UM 之使用者部署的集區相同。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="0d7a4-136">在 **[電話號碼]** 清單中，選取 **[輸入電話號碼]** 或 **[從 Exchange UM 使用此整合通訊接駁電話號碼]**，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="0d7a4-137">在 **[連絡人類型]** 清單中，選取您要建立的連絡人類型，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="0d7a4-138">為您要建立的其他連絡人物件重複步驟 1 到 10。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d7a4-p105">您應該為每個自動語音應答至少建立一個連絡人。如果您想要提供外部存取，也需要具備「訂戶存取」連絡人，並指定直接向內撥號 (DID) 號碼。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="0d7a4-p106">若要確認已經建立了連絡人物件，請開啟 [Active Directory 使用者及電腦]，再選取建立物件的 OU。連絡人物件應會在詳細資料窗格中顯示。</span><span class="sxs-lookup"><span data-stu-id="0d7a4-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="0d7a4-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="0d7a4-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

