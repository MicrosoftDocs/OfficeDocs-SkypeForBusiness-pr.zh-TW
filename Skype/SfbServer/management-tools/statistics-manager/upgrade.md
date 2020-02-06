---
title: 升級商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要：請閱讀本主題，以瞭解如何升級商務用 Skype Server 的統計資料管理器。
ms.openlocfilehash: 6d54261ce9148986df5342bc228fe70b1477e17a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816202"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="6c4fc-103">升級商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="6c4fc-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="6c4fc-104">**摘要：** 若要瞭解如何升級商務用 Skype Server 的統計資料管理員，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="6c4fc-105">本主題描述如何針對商務用 Skype Server 升級現有的統計資料管理員安裝，這是一種強大的工具，可讓您即時查看商務用 Skype Server 健康情況和效能資料。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="6c4fc-106">您可以每隔幾秒在數百個伺服器上輪詢效能資料，並立即在統計資料管理器網站上查看結果。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="6c4fc-107">如需有關統計管理員及版本2.0 中新功能的詳細資訊，請參閱[規劃商務用 Skype server 的統計資料管理器](plan.md)和[部署商務用 Skype Server 的統計資料管理器](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="6c4fc-108">升級的方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="6c4fc-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="6c4fc-109">**自動升級。**</span><span class="sxs-lookup"><span data-stu-id="6c4fc-109">**Automated upgrade.**</span></span> <span data-ttu-id="6c4fc-110">這個方法會使用自動腳本。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-110">This method uses an automated script.</span></span> <span data-ttu-id="6c4fc-111">這是最簡單的方法，且適用于所有升級案例。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="6c4fc-112">**手動升級。**</span><span class="sxs-lookup"><span data-stu-id="6c4fc-112">**Manual upgrade.**</span></span> <span data-ttu-id="6c4fc-113">此方法是在自動升級失敗的情況下以備份方案的形式提供。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="6c4fc-114">先決條件</span><span class="sxs-lookup"><span data-stu-id="6c4fc-114">Prerequisites</span></span>

<span data-ttu-id="6c4fc-115">升級之前，請確定您有下列資訊：</span><span class="sxs-lookup"><span data-stu-id="6c4fc-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="6c4fc-116">Active 監聽器憑證指紋</span><span class="sxs-lookup"><span data-stu-id="6c4fc-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="6c4fc-117">監聽器服務密碼（在安裝監聽器及每個代理程式時輸入）</span><span class="sxs-lookup"><span data-stu-id="6c4fc-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="6c4fc-118">網站的 SSL 憑證設定</span><span class="sxs-lookup"><span data-stu-id="6c4fc-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="6c4fc-119">自動升級</span><span class="sxs-lookup"><span data-stu-id="6c4fc-119">Automated upgrade</span></span>

<span data-ttu-id="6c4fc-120">此腳本會收集您目前的憑證資訊和監聽器密碼、卸載舊版本的產品，然後安裝新版產品。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="6c4fc-121">安裝在伺服器上的 Redis 實例不會被觸摸，因此儲存在快取中的任何資料都會透過升級程式來保留。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="6c4fc-122">針對新版的 agent、監聽器和網站，將 MSI 檔案連同 Update-StatsMan 腳本一起放在監聽器電腦上的單一資料夾中。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="6c4fc-123">開啟 [管理 PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="6c4fc-124">升級攔截器元件：</span><span class="sxs-lookup"><span data-stu-id="6c4fc-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="6c4fc-125">[統計資料管理器] 服務的密碼將會在傳送至安裝程式的命令列上以明文形式顯示。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="6c4fc-126">視需要，請務必遮罩您的監視器。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="6c4fc-127">在執行腳本時，系統會提示您卸載舊版本的產品。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="6c4fc-128">回答 [是]。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="6c4fc-129">如果監聽器服務正在執行，系統會提示您關閉應用程式，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="6c4fc-130">允許應用程式關閉（統計管理員攔截器服務將會停止）。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="6c4fc-131">繼續執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-131">Continue the install process.</span></span> <span data-ttu-id="6c4fc-132">您應該注意到 [服務密碼] 和 [憑證指紋] 是預先填入的。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="6c4fc-133">如果不是，請在繼續之前先加上您所儲存的值。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="6c4fc-134">開啟 [管理 PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="6c4fc-135">升級網站元件：</span><span class="sxs-lookup"><span data-stu-id="6c4fc-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="6c4fc-136">在執行腳本時，系統會提示您卸載舊版本的產品。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="6c4fc-137">回答 [是]。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="6c4fc-138">如果代理服務正在執行，系統會提示您關閉應用程式，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="6c4fc-139">允許應用程式關閉（StatsMan 代理程式服務將停用）。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="6c4fc-140">繼續執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-140">Continue the install process.</span></span> <span data-ttu-id="6c4fc-141">您應該注意到 [服務密碼] 和 [憑證指紋] 是預先填入的。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="6c4fc-142">如果不是，請在繼續之前先加上您所儲存的值。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="6c4fc-143">開啟 [管理 PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="6c4fc-144">升級代理元件：</span><span class="sxs-lookup"><span data-stu-id="6c4fc-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="6c4fc-145">在執行腳本時，系統會提示您卸載舊版本的產品。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="6c4fc-146">回答 [是]。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="6c4fc-147">繼續執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-147">Continue the install process.</span></span> <span data-ttu-id="6c4fc-148">您應該注意到網站埠已預先填入。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="6c4fc-149">如果不是，請先新增您儲存的值，然後繼續。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="6c4fc-150">使用瀏覽器驗證網站是否如預期方式運作。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c4fc-151">您可以將代理升級與-NoPrompt 開關搭配使用。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="6c4fc-152">這可讓卸載/安裝程式以無訊息方式執行，允許諸如 PSExec 之類的工具在大量的伺服器上遠端執行升級。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="6c4fc-153">手動升級</span><span class="sxs-lookup"><span data-stu-id="6c4fc-153">Manual upgrade</span></span>

<span data-ttu-id="6c4fc-154">如果由於某種原因，自動升級失敗，您可以隨時執行手動升級，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c4fc-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="6c4fc-155">在監聽器電腦上，透過 [程式和功能] 控制台卸載監聽器、網站和 Agent （如果它是安裝在此伺服器上）。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="6c4fc-156">保持 Redis 已安裝，以讓快取中的資料能夠透過升級程式維護。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="6c4fc-157">安裝新的元件版本，包括您在系統提示時所儲存的值。</span><span class="sxs-lookup"><span data-stu-id="6c4fc-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="6c4fc-158">如需安裝元件的詳細資訊，請參閱[部署統計資料管理器](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="6c4fc-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="6c4fc-159">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6c4fc-159">For more information</span></span>
<span data-ttu-id="6c4fc-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="6c4fc-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="6c4fc-161">如需詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="6c4fc-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="6c4fc-162">商務用 Skype Server 統計資料的規劃</span><span class="sxs-lookup"><span data-stu-id="6c4fc-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="6c4fc-163">部署商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="6c4fc-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="6c4fc-164">疑難排解商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="6c4fc-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
