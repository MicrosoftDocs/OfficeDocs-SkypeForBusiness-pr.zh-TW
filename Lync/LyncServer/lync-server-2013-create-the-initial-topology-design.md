---
title: Lync Server 2013：建立初始拓撲設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656e9605695fe7dab160469ffa9e9c5075ac807b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="7a98b-102">建立 Lync Server 2013 的初始拓撲設計</span><span class="sxs-lookup"><span data-stu-id="7a98b-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a98b-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7a98b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7a98b-104">在您完成安裝 Lync Server 2013、計畫工具之後，您就可以開始規劃工具並開始設計建議的 Lync Server 2013 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="7a98b-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a98b-105">規劃工具是一個由嚮導驅動的工具，其中包含詳細指南，可在您的網站和拓撲中通知決策過程。</span><span class="sxs-lookup"><span data-stu-id="7a98b-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="7a98b-106">本主題不是完整的指南，只是為了協助您在設計會話中開始使用規劃工具。</span><span class="sxs-lookup"><span data-stu-id="7a98b-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="7a98b-107">開始使用規劃工具並建立初始設計</span><span class="sxs-lookup"><span data-stu-id="7a98b-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="7a98b-108">啟動 Lync Server 2013，規劃工具：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync Server 2013**]，然後按一下 [**規劃工具**]。</span><span class="sxs-lookup"><span data-stu-id="7a98b-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="7a98b-109">開始規劃工具之後，就會出現 [**歡迎使用 Microsoft Lync Server 2013 規劃工具**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7a98b-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="7a98b-110">選擇下列其中一個選項開始進行設計：</span><span class="sxs-lookup"><span data-stu-id="7a98b-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="7a98b-111">**選項1：快速入門**   按一下 **[開始使用**] 提供特定系列的面試問題，以及相關選擇以定義準則。</span><span class="sxs-lookup"><span data-stu-id="7a98b-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="7a98b-112">完成初始 [**開始**進行訪談] 區段後，請繼續進行**設計網站**，以定義您的網站架構。</span><span class="sxs-lookup"><span data-stu-id="7a98b-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="7a98b-113">若要完成此選項，請繼續執行步驟3。</span><span class="sxs-lookup"><span data-stu-id="7a98b-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="7a98b-114">**選項2： [設計網站**   ] 按一下 [歡迎] 頁面上的 [**設計網站**]，即可避開 [**開始**使用] 區段中提供的訪談問題。</span><span class="sxs-lookup"><span data-stu-id="7a98b-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="7a98b-115">若要在 [**開始**使用] 區段中以回復面試問題所收集的資訊，請使用此選項設定為 [預設值]。</span><span class="sxs-lookup"><span data-stu-id="7a98b-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="7a98b-116">只要按一下 [**設計網站**]，經驗豐富的設計工具就能在 [**中央網站**開始] 頁面上略過初始面試，並視需要變更預設值。</span><span class="sxs-lookup"><span data-stu-id="7a98b-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="7a98b-117">若要完成此選項，請跳過步驟3-5，然後從步驟6開始。</span><span class="sxs-lookup"><span data-stu-id="7a98b-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="7a98b-118">**選項3：**   如果您已透過舊版規劃工具完成並儲存拓撲，就會顯示您已儲存的拓撲，您可以略過這些步驟，然後開啟並顯示拓撲。</span><span class="sxs-lookup"><span data-stu-id="7a98b-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="7a98b-119">您也可以對拓撲進行變更與更新、重新儲存，然後將其匯出至 Microsoft Excel 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="7a98b-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="7a98b-120">若要完成此選項，請跳過步驟3-12，然後從步驟13開始。</span><span class="sxs-lookup"><span data-stu-id="7a98b-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="7a98b-121">按一下 [**開始**使用]，開始設計 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="7a98b-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="7a98b-122">針對您的設計選取適當的準則，然後按一下 **[下一步**] 以繼續進行下一個嚮導頁面，以回答每個區段。</span><span class="sxs-lookup"><span data-stu-id="7a98b-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="7a98b-123">按一下 [**返回**]，在前一頁上進行變更。</span><span class="sxs-lookup"><span data-stu-id="7a98b-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7a98b-124">每個頁面都有選取準則的描述，以及根據最佳做法和容量規劃的建議。</span><span class="sxs-lookup"><span data-stu-id="7a98b-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="7a98b-125">如果您需要更多詳細資料，請按一下 [<STRONG>深入瞭解</STRONG>]，以閱讀 Microsoft TechNet 網站上的 Lync Server 2013 規劃檔中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7a98b-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="7a98b-126">您必須具備網際網路連線才能存取 Microsoft TechNet 網站。</span><span class="sxs-lookup"><span data-stu-id="7a98b-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="7a98b-127">針對您的設計選取適當的選項。</span><span class="sxs-lookup"><span data-stu-id="7a98b-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="7a98b-128">定義初始準則之後，頁面將會確認您的功能概述已完成。</span><span class="sxs-lookup"><span data-stu-id="7a98b-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="7a98b-129">按一下 [**設計網站**] 來定義您的中心網站。</span><span class="sxs-lookup"><span data-stu-id="7a98b-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a98b-130">每個 Lync Server 2013 拓撲都至少有一個中心網站。</span><span class="sxs-lookup"><span data-stu-id="7a98b-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="7a98b-131">您的設計可能有單一的中央網站、包含多個分支網站的中央網站、多個中央網站，或與每個中央網站相關聯之分支網站的多個中心網站。</span><span class="sxs-lookup"><span data-stu-id="7a98b-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="7a98b-132">在 [**網站名稱**] 中，輸入要用來識別此中心網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="7a98b-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="7a98b-133">在 [**網站穴使用者**] 中，輸入將駐留在這個中心網站的內部部署併發使用者數。</span><span class="sxs-lookup"><span data-stu-id="7a98b-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="7a98b-134">在**雲端穴使用者**中，輸入將駐留在這個中央網站的預期線上併發使用者數目。</span><span class="sxs-lookup"><span data-stu-id="7a98b-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="7a98b-135">視需要修改線上共同作業、使用者、語音、其他部署選項或伺服器應用程式的選項。</span><span class="sxs-lookup"><span data-stu-id="7a98b-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a98b-136">在設計中的這個階段，您只能選取或清除部署的選項。</span><span class="sxs-lookup"><span data-stu-id="7a98b-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="7a98b-137">不過，您可以在規劃工具的後續階段中設定更多選項。</span><span class="sxs-lookup"><span data-stu-id="7a98b-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="7a98b-138">還有無法使用且無法清除的選項。</span><span class="sxs-lookup"><span data-stu-id="7a98b-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="7a98b-139">此外，您可能必須清除其中一個選項，才能清除另一個選項。</span><span class="sxs-lookup"><span data-stu-id="7a98b-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="7a98b-140">例如，如果您清除 [語音] 底下的 [<STRONG>企業語音</STRONG>] 選項，則會同時清除 [伺服器應用程式] （所有都是企業語音功能）底下的 [<STRONG>回應] 群組</STRONG>、[<STRONG>宣告</STRONG>] 和 [<STRONG>通話駐留</STRONG>] 選項。</span><span class="sxs-lookup"><span data-stu-id="7a98b-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="7a98b-141">定義網站名稱和使用者數量之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7a98b-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="7a98b-142">下列頁面會詢問有關 SIP 網域、會議設定、語音設定和基礎結構、Exchange UM、外部使用者存取、持續聊天設定、客戶設定、collocation 選項和分支網站的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7a98b-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="7a98b-143">請視需要回答這些問題。</span><span class="sxs-lookup"><span data-stu-id="7a98b-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="7a98b-144">最後一個問題會詢問您是否要建立另一個中心網站。</span><span class="sxs-lookup"><span data-stu-id="7a98b-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="7a98b-145">如果您選取 **[是]**，則規劃工具會回到 [中央網站] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7a98b-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="7a98b-146">如果您選取 [**否**]，請按 **[下一步]**，然後按一下 [**繪圖**] 以顯示 [高層次] 全域拓撲圖視圖。</span><span class="sxs-lookup"><span data-stu-id="7a98b-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="7a98b-147">若要查看現有的拓撲，請按一下 [**顯示**]。</span><span class="sxs-lookup"><span data-stu-id="7a98b-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="7a98b-148">按一下代表先前儲存拓撲的 .xml 檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7a98b-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="7a98b-149">規劃工具會顯示 [全域拓撲] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7a98b-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="7a98b-150">您現在可以使用規劃工具中提供的工具開始編輯、更新或變更拓撲。</span><span class="sxs-lookup"><span data-stu-id="7a98b-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a98b-151">請參閱</span><span class="sxs-lookup"><span data-stu-id="7a98b-151">See Also</span></span>


[<span data-ttu-id="7a98b-152">在 Lync Server 2013 中編輯設計</span><span class="sxs-lookup"><span data-stu-id="7a98b-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

