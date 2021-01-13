---
title: 為商務用 Skype Server 2015 建立初始拓撲設計
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: 在您完成安裝商務用 Skype Server 規劃工具後，您就可以開始規劃工具及開始設計擬議中的商務用 Skype Server 2015 基礎結構。
ms.openlocfilehash: 7de930de8d7e194f14145c1a976fbe6b96cf234a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834963"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a><span data-ttu-id="beaa5-103">為商務用 Skype Server 2015 建立初始拓撲設計</span><span class="sxs-lookup"><span data-stu-id="beaa5-103">Create the initial topology design for Skype for Business Server 2015</span></span>

<span data-ttu-id="beaa5-104">在您完成安裝商務用 Skype Server 規劃工具後，您就可以開始規劃工具及開始設計擬議中的商務用 Skype Server 2015 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="beaa5-104">After you have finished installing the Skype for Business Server Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Skype for Business Server 2015 infrastructure.</span></span>

> [!NOTE]
>  <span data-ttu-id="beaa5-105">規劃工具是一個嚮導導向工具，具有詳細的指南，可在設計網站和拓撲時通知決策過程。</span><span class="sxs-lookup"><span data-stu-id="beaa5-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="beaa5-106">本主題的目的不是詳盡的指南，只是協助您在設計會話中開始使用規劃工具。</span><span class="sxs-lookup"><span data-stu-id="beaa5-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="beaa5-107">開始使用規劃工具及建立初始設計</span><span class="sxs-lookup"><span data-stu-id="beaa5-107">To get started using the Planning Tool and create the initial design</span></span>

1. <span data-ttu-id="beaa5-108">啟動商務用 Skype Server 2015 規劃工具：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 Skype 伺服器 2015**]，然後按一下 [ **規劃工具**]。</span><span class="sxs-lookup"><span data-stu-id="beaa5-108">Start the Skype for Business Server 2015 Planning Tool: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Planning Tool**.</span></span>

2. <span data-ttu-id="beaa5-109">在規劃工具開始之後，就會出現 [ **歡迎使用商務用 Skype Server 2015 的規劃工具** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="beaa5-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Skype for Business Server 2015** page appears.</span></span> <span data-ttu-id="beaa5-110">選擇下列其中一個選項來開始您的設計：</span><span class="sxs-lookup"><span data-stu-id="beaa5-110">Choose one of the following options to begin your design:</span></span>

   - <span data-ttu-id="beaa5-111">**選項1：快速入門** 按一下 [ **開始** 使用] 提供特定系列的採訪問題，以及相關選擇以定義準則。</span><span class="sxs-lookup"><span data-stu-id="beaa5-111">**Option 1: Get Started** Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="beaa5-112">當您完成最初的「 **入門** 面試」區段之後，請繼續進行 **設計網站** 以定義您的網站架構。</span><span class="sxs-lookup"><span data-stu-id="beaa5-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="beaa5-113">若要完成此選項，請繼續進行步驟3。</span><span class="sxs-lookup"><span data-stu-id="beaa5-113">To complete this option, proceed to step 3.</span></span>

   - <span data-ttu-id="beaa5-114">**選項2：設計網站** 按一下 [歡迎] 頁面上的 [ **設計網站** ]，可以略過「 **開始** 使用」區段中的 [面試問題]。</span><span class="sxs-lookup"><span data-stu-id="beaa5-114">**Option 2: Design Sites** Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="beaa5-115">使用此選項，以回應「 **開始** 使用」區段中的「面試問題」區段所收集到的資訊將會設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="beaa5-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="beaa5-116">透過按一下 [ **設計網站**]，經驗豐富的設計者可以略過初次面試，並視需要在 [ **中央網站** 開始] 頁面上變更預設值。</span><span class="sxs-lookup"><span data-stu-id="beaa5-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="beaa5-117">若要完成此選項，請略過步驟3-5，並從步驟6開始。</span><span class="sxs-lookup"><span data-stu-id="beaa5-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>

   - <span data-ttu-id="beaa5-118">**選項3：顯示您儲存的拓撲** 如果您已透過先前使用規劃工具完成並儲存拓撲，您可以略過這些步驟，然後開啟並顯示拓撲。</span><span class="sxs-lookup"><span data-stu-id="beaa5-118">**Option 3: Display Your Saved Topology** If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="beaa5-119">您也可以對拓撲進行變更和更新，並重新保存，然後將它匯出至 Microsoft Excel 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="beaa5-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="beaa5-120">若要完成此選項，請略過步驟3-12，並從步驟13開始。</span><span class="sxs-lookup"><span data-stu-id="beaa5-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3. <span data-ttu-id="beaa5-121">按一下 [ **開始** ]，開始設計商務用 Skype Server 2015 拓撲。</span><span class="sxs-lookup"><span data-stu-id="beaa5-121">Click **Get Started** to begin designing your Skype for Business Server 2015 topology.</span></span>

4. <span data-ttu-id="beaa5-122">請選取您設計的適當準則，然後按 **[下一步** ] 繼續進行下一個嚮導頁面，以回答每一節。</span><span class="sxs-lookup"><span data-stu-id="beaa5-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="beaa5-123">按一下 [ **上一步** ]，在先前頁面上進行變更。</span><span class="sxs-lookup"><span data-stu-id="beaa5-123">Click **Back** to make changes on previous pages.</span></span>

    > [!TIP]
    > <span data-ttu-id="beaa5-124">每一頁都有選取準則的描述，以及根據慣用做法和容量規劃的建議。</span><span class="sxs-lookup"><span data-stu-id="beaa5-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="beaa5-125">如果您需要其他詳細資料，請按一下 [ **深入瞭解** ]，以閱讀 Microsoft 網站上商務用 Skype Server 2015 規劃檔中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="beaa5-125">If you require additional details, click **Learn more** to read detailed information from the Skype for Business Server 2015 Planning documentation on the Microsoft  website.</span></span> <span data-ttu-id="beaa5-126">您必須具有網際網路連線才能存取 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="beaa5-126">You must have Internet connectivity to access the Microsoft  website.</span></span>

5. <span data-ttu-id="beaa5-127">為您的設計選取適當的選項。</span><span class="sxs-lookup"><span data-stu-id="beaa5-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="beaa5-128">在定義初始準則之後，頁面會確認您的功能概述已完成。</span><span class="sxs-lookup"><span data-stu-id="beaa5-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6. <span data-ttu-id="beaa5-129">按一下 [ **設計網站** ] 以定義您的中央網站。</span><span class="sxs-lookup"><span data-stu-id="beaa5-129">Click **Design Sites** to define your central site.</span></span>

    > [!NOTE]
    > <span data-ttu-id="beaa5-130">每個商務用 Skype Server 2015 拓撲至少會有一個中央網站。</span><span class="sxs-lookup"><span data-stu-id="beaa5-130">Each Skype for Business Server 2015 topology will have at least one central site.</span></span> <span data-ttu-id="beaa5-131">您的設計可能有單一中央網站、包含許多分支網站的中央網站、許多中央網站，或具有與每個中央網站相關聯之分支網站的中央網站數目。</span><span class="sxs-lookup"><span data-stu-id="beaa5-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

7. <span data-ttu-id="beaa5-132">在 [ **網站名稱**] 中，輸入要識別此中央網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="beaa5-132">In **Site Name**, type the name that will identify this central site.</span></span>

8. <span data-ttu-id="beaa5-133">在 [ **網站主使用者**] 中，輸入將裝載于此中央網站中的內部部署並行使用者數目。</span><span class="sxs-lookup"><span data-stu-id="beaa5-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9. <span data-ttu-id="beaa5-134">在 [ **雲端主使用者**] 中，輸入將位於此中央網站的預期線上並行使用者數目。</span><span class="sxs-lookup"><span data-stu-id="beaa5-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="beaa5-135">視需要，修改線上共同作業、使用者、語音、其他部署選項或伺服器應用程式的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="beaa5-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="beaa5-136">在設計的此階段，您只可以選取或清除部署的選項。</span><span class="sxs-lookup"><span data-stu-id="beaa5-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="beaa5-137">不過，您可以在規劃工具的後續階段中設定更多選項。</span><span class="sxs-lookup"><span data-stu-id="beaa5-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="beaa5-138">也有無法使用且無法清除的選項。</span><span class="sxs-lookup"><span data-stu-id="beaa5-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="beaa5-139">此外，您可能需要清除其中一個選項，才能清除另一個選項。</span><span class="sxs-lookup"><span data-stu-id="beaa5-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="beaa5-140">例如，如果您清除 [語音] 底下的 [ **Enterprise Voice** ] 選項，則 [伺服器應用程式] 下的 [ **回應群組**]、[ **宣告**] 和 [ **通話駐留** ] 選項會同時清除 [伺服器應用程式] 下的 [ (所有功能]) 。</span><span class="sxs-lookup"><span data-stu-id="beaa5-140">For example, if you clear the **Enterprise Voice** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

11. <span data-ttu-id="beaa5-141">定義網站名稱和使用者數目後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="beaa5-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="beaa5-142">下列頁面要求有關 SIP 網域、會議設定、語音設定和基礎結構、Exchange UM、外部使用者存取、持續聊天設定、用戶端設定、組合選項及分支網站的資訊。</span><span class="sxs-lookup"><span data-stu-id="beaa5-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="beaa5-143">請視需要回答這些問題。</span><span class="sxs-lookup"><span data-stu-id="beaa5-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="beaa5-144">最後一個問題會詢問您是否要建立另一個中央網站。</span><span class="sxs-lookup"><span data-stu-id="beaa5-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="beaa5-145">如果您選取 **[是]**，則規劃工具會傳回 [中央網站] 頁面。</span><span class="sxs-lookup"><span data-stu-id="beaa5-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="beaa5-146">如果您選取 [ **否**]，請按 **[下一步]**，然後按一下 [ **繪圖** ] 顯示高層級通用拓撲視圖。</span><span class="sxs-lookup"><span data-stu-id="beaa5-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="beaa5-147">若要查看現有的拓撲，請按一下 [ **顯示**]。</span><span class="sxs-lookup"><span data-stu-id="beaa5-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="beaa5-148">按一下代表先前儲存的拓撲的 .xml 檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="beaa5-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="beaa5-149">規劃工具會顯示 [全域拓撲] 頁面。</span><span class="sxs-lookup"><span data-stu-id="beaa5-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="beaa5-150">您現在可以使用規劃工具中提供的工具開始編輯、更新或變更拓撲。</span><span class="sxs-lookup"><span data-stu-id="beaa5-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="beaa5-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="beaa5-151">See also</span></span>

[<span data-ttu-id="beaa5-152">編輯設計</span><span class="sxs-lookup"><span data-stu-id="beaa5-152">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
