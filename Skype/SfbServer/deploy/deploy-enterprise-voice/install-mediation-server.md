---
title: 在商務用 Skype Server 中安裝用於轉送服務伺服器的檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '摘要: 瞭解如何在商務用 Skype Server 中安裝用於轉送作業伺服器的檔案。'
ms.openlocfilehash: 8ecd5b20f7f3dfac625851c94f313a50fa71af29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193149"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="91622-103">在商務用 Skype Server 中安裝用於轉送服務伺服器的檔案</span><span class="sxs-lookup"><span data-stu-id="91622-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="91622-104">**摘要:** 瞭解如何在商務用 Skype Server 中安裝用於轉送轉送伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="91622-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="91622-105">若要成功完成這個程式, 您應該至少以本機系統管理員和至少擁有 RTCUniversalReadOnlyAdmins 群組成員資格的網域使用者的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="91622-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="91622-106">使用本主題中的步驟, 執行商務用 Skype Server 部署嚮導, 在您已使用拓撲建立器定義及發佈池之後, 在您新增到轉送伺服器池中的電腦上安裝轉送服務伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="91622-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="91622-107">在安裝檔轉送伺服器時, 您也會安裝並指派中繼伺服器池中每個電腦所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="91622-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="91622-108">本主題假設您已在您的拓撲中定義併發布獨立的轉送伺服器池, 如在商務用 Skype Server 的 [拓撲建立器] 中[部署轉送伺服器](deploy-a-mediation-server.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="91622-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="91622-109">若要為獨立的中繼伺服器池安裝檔案</span><span class="sxs-lookup"><span data-stu-id="91622-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="91622-110">在安裝媒體中, 以滑鼠右鍵按一下_ \<[\>安裝媒體_ **\Setup\amd64\Setup.exe**], 然後按一下 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="91622-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="91622-111">在 [**安裝位置**] 頁面上, 按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="91622-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="91622-112">在 [**使用者授權合約**] 頁面上, 按一下 [**我接受**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="91622-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="91622-113">(需要才能繼續)。</span><span class="sxs-lookup"><span data-stu-id="91622-113">(Required to continue.)</span></span>
    
4. <span data-ttu-id="91622-114">在 [**商務用 Skype Server 部署嚮導]** 頁面上, 按一下 [**安裝或更新商務用 Skype server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="91622-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="91622-115">在 [**步驟 1: 安裝本機設定儲存區**] 旁, 按一下 [**執行**], 然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="91622-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="91622-116">在 [**設定中央管理儲存的本機複本**] 頁面上, 接受 **[直接從中央管理存儲**的預設檢索], 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="91622-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="91622-117">在 [**執行命令**] 頁面上, 當任務狀態顯示為 [**完成**] 時, 按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="91622-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="91622-118">在 [**步驟 2: 設定] 或 [移除商務用 Skype 伺服器元件**] 旁, 按一下 [**執行**], 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="91622-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="91622-119">在 [**執行命令**] 頁面上, 當任務狀態顯示為 [**完成**] 時, 按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="91622-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="91622-120">在**步驟 3: 要求、安裝或指派憑證**, 按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="91622-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="91622-121">依照畫面上的指示進行, 接受預設設定。</span><span class="sxs-lookup"><span data-stu-id="91622-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="91622-122">中繼伺服器需要一個憑證, 因此您執行的**步驟 3**兩次: 一次是頒發所需的憑證, 然後再將它指派給您。</span><span class="sxs-lookup"><span data-stu-id="91622-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="91622-123">在證書已頒發並指派正確之後, 在**步驟 4: 啟動服務**, 按一下 [**執行**], 然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="91622-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="91622-124">當**步驟 4**成功完成時, 請重新開機伺服器, 並以 DomainAdmins 群組成員的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="91622-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="91622-125">在您執行商務用 Skype Server 控制台的電腦上, 確認已將中繼伺服器的服務狀態顯示為綠色核取記號, 並在商務用 Skype Server [控制台] 的 [**拓撲**] 頁面上進行驗證。</span><span class="sxs-lookup"><span data-stu-id="91622-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="91622-126">如果改為顯示紅色 X, 請選取中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="91622-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="91622-127">在 [**動作**] 功能表上, 按一下 [**啟動所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="91622-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="91622-128">如果您在中繼伺服器池中新增多個電腦, 請在轉送伺服器池中的所有其他電腦上執行此程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="91622-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="91622-129">如果您不需要為任何其他電腦安裝轉送伺服器的檔案, 請遵循在[商務用 Skype server 中設定 trunks 中](configure-trunks.md)的程式, 以設定此中繼伺服器池 (或所有轉送) 之間主幹連接的設定。網站上的伺服器) 及其對等。</span><span class="sxs-lookup"><span data-stu-id="91622-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

