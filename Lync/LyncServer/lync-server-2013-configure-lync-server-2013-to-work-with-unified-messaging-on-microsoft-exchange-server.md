---
title: Lync Server 2013：設定 Lync Server 2013 以搭配 Microsoft Exchange Server 上的 Unified Messaging 使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="4a9c9-102">設定 Lync Server 2013 以搭配 Microsoft Exchange Server 上的 Unified Messaging 使用</span><span class="sxs-lookup"><span data-stu-id="4a9c9-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="4a9c9-103">_**主題上次修改日期：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="4a9c9-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="4a9c9-104">此步驟需要 Exchange UM 整合實用程式（OcsUmUtil）。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="4a9c9-105">此工具位於 Lync Server 2013 伺服器上的。\\Program files\\常見檔案\\Microsoft Lync Server 2013\\支援資料夾。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="4a9c9-106">執行 Exchange UM 整合公用程式</span><span class="sxs-lookup"><span data-stu-id="4a9c9-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="4a9c9-107">Exchange UM 整合公用程式必須從具有下列特性的使用者帳戶執行：</span><span class="sxs-lookup"><span data-stu-id="4a9c9-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="4a9c9-108">RTCUniversalServerAdmins 和 RtcUniversalUserAdmins 群組中的成員資格（包含讀取 Exchange Server 整合通訊設定的許可權）。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="4a9c9-109">網域中的使用者權利，可在指定的組織單位（OU）容器中建立連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="4a9c9-110">當您執行 Exchange UM 整合公用程式時，會執行下列任務：</span><span class="sxs-lookup"><span data-stu-id="4a9c9-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="4a9c9-111">針對企業語音使用者所要使用的每個自動助理和使用者存取號碼建立連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="4a9c9-112">驗證每個企業語音撥號方案的名稱是否符合其對應的 [統一訊息（UM）撥號方案電話] 內容。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="4a9c9-113">只有在 Exchange 2010 Service Pack 1 （SP1）*之前*的 exchange 版本上執行 UM 撥號方案時，才能使用這個相符。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a9c9-114">在執行 Exchange UM 整合公用程式前，請確定您已完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="4a9c9-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="4a9c9-115">建立一或多個 Exchange UM 撥號方案，如 Exchange 產品檔中所述。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="4a9c9-116">若為 Microsoft Exchange Server 2010， &quot;請參閱在<a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>建立 UM&quot;撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="4a9c9-117">如果您使用的是 Microsoft Exchange Server 2007 Service Pack 1 （ &quot;SP1），請參閱如何在<a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>建立整合通訊&quot; SIP URI 撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="4a9c9-118">如在<a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 中建立撥號方案</a>中所述，建立一個或多個對應的 Lync server 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="4a9c9-119">如果您使用的 Exchange 版本早于 Microsoft Exchange Server 2010 SP1，您必須在 Lync Server 2013 撥號方案 [<STRONG>簡易名稱</STRONG>] 欄位中輸入對應 Exchange 整合訊息（UM） SIP 撥號方案的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="4a9c9-120">如果您使用的是 Microsoft Exchange Server 2010 SP1 或最新的 service pack，則不需要這種撥號方案名稱相符。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="4a9c9-121">建立自動助理，並確認使用者存取號碼和自動助理號碼的格式為：164。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="4a9c9-122">若要執行 Exchange UM 整合公用程式</span><span class="sxs-lookup"><span data-stu-id="4a9c9-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="4a9c9-123">在前端伺服器上，開啟命令提示字元，然後輸入**cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\支援**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="4a9c9-124">輸入**OcsUmUtil**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="4a9c9-125">按一下 [**載入資料**] 以尋找所有受信任的 Exchange 目錄林。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="4a9c9-126">在 [ **SIP 撥號方案**] 清單中，選取您要為其建立連絡人物件的 UM SIP 撥號方案，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="4a9c9-127">在 [**連絡人**] 方塊中，接受預設組織單位，或按一下 **[流覽]** 以啟動**OU 選擇器**。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="4a9c9-128">在 [ **OU 選擇器**] 方塊中，您可以選取一個 ou 並按一下 **[確定]**，或按一下 [**建立新的 OU** ]，在網域的根目錄或任何其他 ou （例如，「OU = RTC 特殊帳戶、dc =.、dc = com」）中建立新的組織單位，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a9c9-129">您已選取或建立之 OU 的辨識名稱（DN）現在會顯示在 [<STRONG>組織單位</STRONG>] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="4a9c9-130">在 [**名稱**] 方塊中，接受預設的撥號計畫名稱，或針對您要建立的連絡人物件輸入新的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a9c9-131">例如，如果您要建立訂閱者 access 連絡人物件，可能只需將其命名為訂閱者存取。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="4a9c9-132">在 [ **SIP 位址**] 方塊中，您可以接受預設的 sip 位址，或輸入新的 sip 位址。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a9c9-133">如果您輸入新的 SIP 位址，它必須以<STRONG>SIP 開頭：</STRONG> （也就是「SIP：」包括冒號）。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="4a9c9-134">在 [**伺服器] 或 [池**] 清單中，選取要啟用連絡人物件的標準版伺服器或 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a9c9-135">最好的是，您所選取的 [池] 就是部署啟用企業語音和 Exchange UM 之使用者的同一個池。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="4a9c9-136">在 [**電話號碼**] 清單中，選取 [**輸入電話號碼**] 或 [**從 Exchange UM 使用這個試驗號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="4a9c9-137">在 [**連絡人類型**] 清單中，選取您要建立的連絡人類型，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="4a9c9-138">針對您想要建立的其他連絡人物件，重複步驟1到10。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a9c9-139">您至少應該為每個自動語音助理建立一個連絡人。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="4a9c9-140">如果您想要外部存取，您也需要訂閱者存取連絡人，並指定直接撥出電話（已有）號碼。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="4a9c9-141">若要確認已建立連絡人物件，請開啟 [Active Directory 使用者和電腦]，然後選取在其中建立物件的 OU。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="4a9c9-142">連絡人物件應該會出現在 [詳細資料] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="4a9c9-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="4a9c9-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="4a9c9-143"></span></span></div>

