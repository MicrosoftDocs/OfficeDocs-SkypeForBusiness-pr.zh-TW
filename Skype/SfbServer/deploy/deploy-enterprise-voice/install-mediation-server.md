---
title: 在商務用 Skype Server 中安裝轉送伺服器的檔案
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 摘要：瞭解如何在商務用 Skype Server 中安裝轉送伺服器的檔案。
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830793"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="94e6c-103">在商務用 Skype Server 中安裝轉送伺服器的檔案</span><span class="sxs-lookup"><span data-stu-id="94e6c-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="94e6c-104">**摘要：** 瞭解如何在商務用 Skype Server 中安裝轉送伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="94e6c-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="94e6c-105">若要順利完成此程式，您應該至少以本機系統管理員身分登入伺服器，以及至少擁有 RTCUniversalReadOnlyAdmins 群組成員資格的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="94e6c-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="94e6c-106">使用本主題中的步驟執行商務用 Skype Server 部署嚮導，在您已使用拓撲產生器來定義及發行集區之後，在已新增至轉送伺服器集區的電腦上，安裝轉送伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="94e6c-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="94e6c-107">在安裝檔轉送伺服器時，您也會安裝並指派轉送伺服器集區中每一部電腦所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="94e6c-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="94e6c-108">本主題假設您已在拓撲中定義及發行獨立的轉送伺服器集區，如在 [商務用 Skype server 的拓撲](deploy-a-mediation-server.md)產生器中部署轉送伺服器所述。</span><span class="sxs-lookup"><span data-stu-id="94e6c-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="94e6c-109">若要為獨立的轉送伺服器集區安裝檔案</span><span class="sxs-lookup"><span data-stu-id="94e6c-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="94e6c-110">在安裝媒體中，以滑鼠右鍵按一下 [  _\<installation media\>_ **\Setup\amd64\Setup.exe**]，然後按一下 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="94e6c-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="94e6c-111">在 [ **安裝位置** ] 頁面上，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="94e6c-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="94e6c-112">在 [ **使用者授權合約** ] 頁面上，按一下 [ **我接受**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="94e6c-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="94e6c-113">需要 (才能繼續。 ) </span><span class="sxs-lookup"><span data-stu-id="94e6c-113">(Required to continue.)</span></span>
    
4. <span data-ttu-id="94e6c-114">在 [ **商務用 Skype 伺服器部署嚮導]** 頁面上，按一下 [ **安裝或更新商務用 Skype server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="94e6c-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="94e6c-115">在 [ **步驟1：安裝本機設定存放區**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="94e6c-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="94e6c-116">在 [ **設定中央管理存放區的本機複本** ] 頁面上，接受 **直接從中央管理存放區進行** 的預設檢索，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="94e6c-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="94e6c-117">在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="94e6c-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="94e6c-118">在 [ **步驟2：安裝或移除商務用 Skype 伺服器元件**] 旁邊，按一下 [ **執行**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="94e6c-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="94e6c-119">在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="94e6c-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="94e6c-120">在 [ **步驟3：要求、安裝或指派憑證**] 旁邊，按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="94e6c-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="94e6c-121">依照畫面上的指示，接受預設設定。</span><span class="sxs-lookup"><span data-stu-id="94e6c-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="94e6c-122">轉送伺服器需要一個憑證，因此您將執行 **步驟 3** 兩次：一次發出必要的憑證，再進行指派。</span><span class="sxs-lookup"><span data-stu-id="94e6c-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="94e6c-123">當憑證已正確發行並指派正確時，在 [ **步驟4：啟動服務**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="94e6c-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="94e6c-124">當 **步驟 4** 成功完成後，請重新開機伺服器，並以 DomainAdmins 群組成員的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="94e6c-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="94e6c-125">在您執行商務用 Skype Server 控制台的電腦上，確認轉送伺服器的服務狀態顯示為綠色核取記號，商務用 Skype Server 控制台的 [ **拓撲** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="94e6c-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="94e6c-126">若改為顯示紅色 X，請選取轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="94e6c-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="94e6c-127">在 [ **動作** ] 功能表上，按一下 [ **啟動所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="94e6c-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="94e6c-128">如果您已將一部以上的電腦新增至轉送伺服器集區，請在轉送伺服器集區中的所有其他電腦上，執行此程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="94e6c-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="94e6c-129">如果您不需要為其他任何電腦安裝轉送伺服器的檔案，請遵循 [configure 主幹 In 商務用 Skype server](configure-trunks.md) 中的程式來設定此轉送伺服器集區 (或所有轉送伺服器（位於網站) 及其對等）之間的主幹連線設定。</span><span class="sxs-lookup"><span data-stu-id="94e6c-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

