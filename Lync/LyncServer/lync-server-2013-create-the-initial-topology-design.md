---
title: Lync Server 2013： 建立初始拓撲設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ccdec2c39839674c6304000680ec611a48c016
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="2f0d0-102">建立初始拓撲設計的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f0d0-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f0d0-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="2f0d0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2f0d0-104">當您完成安裝 Lync Server 2013 規劃工具之後, 您準備好要開始規劃工具，並開始設計建議的 Lync Server 2013 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f0d0-105">規劃工具是精靈驅動的工具與詳細的指南，以通知您在設計您的網站和拓樸的決策程序。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="2f0d0-106">本主題旨在不太詳盡快顯功能表中，但只是要幫助您開始使用規劃工具設計工作階段中。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="2f0d0-107">若要開始使用規劃工具，並建立初始設計</span><span class="sxs-lookup"><span data-stu-id="2f0d0-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="2f0d0-108">啟動 Lync Server 2013 規劃工具： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**規劃工具**。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="2f0d0-109">開始規劃工具後，便會出現 [**歡迎使用 Microsoft Lync Server 2013 規劃工具**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="2f0d0-110">選擇下列其中一個下列選項來開始設計：</span><span class="sxs-lookup"><span data-stu-id="2f0d0-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="2f0d0-111">**選項 1： 開始**   按一下**開始**提供特定的一系列採訪問題與相關選項來定義的準則。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="2f0d0-112">完成初始**開始**面試] 區段中之後，您在繼續進行來定義網站架構**設計站台**。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="2f0d0-113">若要完成此選項，繼續進行步驟 3。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="2f0d0-114">**選項 2： 設計站台**   [歡迎] 頁面上，按一下**設計站台**會略過 [**開始**] 區段中所述的採訪問題。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="2f0d0-115">會藉由回應**快速入門**] 區段中的採訪問題收集的資訊設為使用此選項的預設值。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="2f0d0-116">按一下 [**設計站台**，資深的設計師可以略過初始採訪，且預設值，視需要變更，在**中央網站**的 [開始] 畫面。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="2f0d0-117">若要完成此選項，略過步驟 3-5，開始執行步驟 6。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="2f0d0-118">**選項 3： 顯示您儲存拓撲**   如果您已完成並儲存到先前使用規劃工具的拓撲，您可以略過大部分的步驟，並藉由開啟並顯示拓樸開始。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="2f0d0-119">您可以也對拓撲進行的變更和更新，重新儲存它，然後將它匯出至 Microsoft Excel 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="2f0d0-120">若要完成此選項，略過步驟 3-12，開始執行步驟 13。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="2f0d0-121">按一下 [開始設計您的 Lync Server 2013 拓撲的 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="2f0d0-122">藉由選取適當的條件，對您的設計，回答每一節，然後按一下 [**下一步**] 精靈的下一頁繼續。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="2f0d0-123">按一下 [**上一步**之前的頁面上進行變更。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2f0d0-124">每一頁有選取準則，並根據慣用的作法和容量規劃的建議的描述。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="2f0d0-125">如果您需要額外的詳細資訊，請按一下 [<STRONG>更多的了解</STRONG>讀取在 Microsoft TechNet 網站上的 Lync Server 2013 規劃文件的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="2f0d0-126">您必須具有網際網路連線能力存取 Microsoft TechNet 網站。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="2f0d0-127">選取您的設計的適當選項。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="2f0d0-128">初始的準則定義之後，頁面會確認完成功能概觀。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="2f0d0-129">按一下 [**設計站台**來定義您的中央網站。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f0d0-130">每個 Lync Server 2013 拓撲會有至少一個中央網站。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="2f0d0-131">單一中央站台、 中央網站與分支網站數目、 中央網站數目、 或與每個中央網站相關聯的分公司站台的中央網站的數目，可能需要您的設計。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="2f0d0-132">在 [**網站名稱**] 中，輸入會識別此中央網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="2f0d0-133">在**網站位於使用者**]，輸入預期的內部並行使用者將會位於此中央網站的數目。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="2f0d0-134">在**雲端位於使用者**]，輸入預期線上並行使用者將會位於此中央網站的數目。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="2f0d0-135">視需要修改線上共同作業、 使用者、 語音、 其他部署選項，或伺服器應用程式] 選項。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2f0d0-136">此時在設計中，您可以只選取或清除選項為您的部署。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="2f0d0-137">不過，您可以在稍後階段中規劃工具的設定更多選項]。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="2f0d0-138">也有無法使用，無法清除選項。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="2f0d0-139">此外，您可能必須清除以清除另一個選項。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="2f0d0-140">例如，如果您同時清除下語音，然後<STRONG>回應群組</STRONG>，<STRONG>宣告</STRONG>的<STRONG>Enterprise Voice</STRONG>選項和<STRONG>通話駐留</STRONG>（它們都是企業語音功能） 的伺服器應用程式] 之下的選項也會取消選取。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="2f0d0-141">定義站台名稱和使用者數量後, 按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="2f0d0-142">下列頁面詢問資訊的 SIP 網域、 會議設定、 語音設定和基礎結構、 Exchange UM、 外部使用者存取、 常設聊天室設定、 用戶端設定、 組合的選項，以及分支站台。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="2f0d0-143">回答這些問題，視。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="2f0d0-144">最後一個問題會要求您若要建立另一個中央網站。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="2f0d0-145">如果您選取 [**是**]，然後規劃工具傳回中央網站] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="2f0d0-146">如果您選取 [**否]**，按一下 [**下一步**，，，然後按一下 [先顯示的高層級的全域拓撲檢視**繪製**。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="2f0d0-147">若要檢視現有的拓樸，按一下 [**顯示**]。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="2f0d0-148">按一下表示之前儲存的拓撲的.xml 檔案，然後按一下 [**開啟**。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="2f0d0-149">規劃工具會顯示 [全域拓撲] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="2f0d0-150">您現在可以開始編輯、 更新或使用規劃工具中可用的工具來變更拓樸。</span><span class="sxs-lookup"><span data-stu-id="2f0d0-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f0d0-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2f0d0-151">See Also</span></span>


[<span data-ttu-id="2f0d0-152">編輯 Lync Server 2013 中的設計</span><span class="sxs-lookup"><span data-stu-id="2f0d0-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

