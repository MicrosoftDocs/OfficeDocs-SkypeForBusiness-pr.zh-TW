---
title: 升級商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要：閱讀此主題以瞭解如何升級商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821763"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="dbbaf-103">升級商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="dbbaf-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="dbbaf-104">**摘要：** 閱讀此主題以瞭解如何升級商務用 Skype Server 的統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="dbbaf-105">本主題說明如何為商務用 Skype Server 升級現有的統計資料管理員安裝功能，這是一種強大的工具，可讓您即時查看商務用 Skype 伺服器的健康情況和效能資料。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="dbbaf-106">您可以每隔幾秒輪詢每數百部伺服器上的效能資料，並在統計資料管理員網站上立即查看結果。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="dbbaf-107">如需有關統計資料管理員的詳細資訊，以及版本2.0 中的新功能，請參閱 [Plan For 商務用 Skype server 的統計資料管理員](plan.md) 和 [部署商務用 Skype Server 的統計資料管理員](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="dbbaf-108">有兩種升級方法：</span><span class="sxs-lookup"><span data-stu-id="dbbaf-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="dbbaf-109">**自動升級。**</span><span class="sxs-lookup"><span data-stu-id="dbbaf-109">**Automated upgrade.**</span></span> <span data-ttu-id="dbbaf-110">此方法使用自動腳本。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-110">This method uses an automated script.</span></span> <span data-ttu-id="dbbaf-111">這是最簡單的方法，且應該適用于所有的升級案例。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="dbbaf-112">**手動升級。**</span><span class="sxs-lookup"><span data-stu-id="dbbaf-112">**Manual upgrade.**</span></span> <span data-ttu-id="dbbaf-113">這種方法是一種備份計畫，在這種情況下，自動升級失敗的情況很少見。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="dbbaf-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="dbbaf-114">Prerequisites</span></span>

<span data-ttu-id="dbbaf-115">在升級之前，請確定您有下列資訊：</span><span class="sxs-lookup"><span data-stu-id="dbbaf-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="dbbaf-116">主動攔截器憑證指紋</span><span class="sxs-lookup"><span data-stu-id="dbbaf-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="dbbaf-117">在安裝監聽器及每個代理人) 時輸入的監聽器服務密碼 (</span><span class="sxs-lookup"><span data-stu-id="dbbaf-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="dbbaf-118">網站的 SSL 憑證設定</span><span class="sxs-lookup"><span data-stu-id="dbbaf-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="dbbaf-119">自動升級</span><span class="sxs-lookup"><span data-stu-id="dbbaf-119">Automated upgrade</span></span>

<span data-ttu-id="dbbaf-120">腳本會收集您目前的憑證資訊和監聽器密碼、卸載舊版本的產品，然後安裝新版本的產品。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="dbbaf-121">將不會接觸安裝在伺服器上的 Redis 實例，因此儲存在快取中的任何資料都會透過升級程式保留。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="dbbaf-122">將新版本的代理程式、監聽器和網站的 MSI 檔案，放入監聽器電腦上的單一資料夾中，同時將 Update-StatsMan.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="dbbaf-123">開啟 [管理 PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="dbbaf-124">升級攔截器元件：</span><span class="sxs-lookup"><span data-stu-id="dbbaf-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="dbbaf-125">在傳送至安裝程式時，會在命令列上以純文字顯示統計資料管理員服務密碼。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="dbbaf-126">請務必視需要遮罩監視器。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="dbbaf-127">在執行腳本時，您應該會收到卸載舊版本產品的提示。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="dbbaf-128">答案是。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="dbbaf-129">如果正在執行監聽器服務，系統會提示您關閉應用程式，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="dbbaf-130">允許應用程式關閉 (統計資料管理員偵聽程式服務將停止) 。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="dbbaf-131">繼續執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-131">Continue the install process.</span></span> <span data-ttu-id="dbbaf-132">您應該會發現服務密碼和憑證指紋已預先填入。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="dbbaf-133">如果不是，請在繼續之前先新增您儲存的值。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="dbbaf-134">開啟 [管理 PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="dbbaf-135">升級網站元件：</span><span class="sxs-lookup"><span data-stu-id="dbbaf-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="dbbaf-136">在執行腳本時，您應該會收到卸載舊版本產品的提示。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="dbbaf-137">答案是。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="dbbaf-138">如果代理程式服務正在執行，系統會提示您關閉應用程式，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="dbbaf-139">允許應用程式在 StatsMan 代理程式服務) 停止時關閉 (。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="dbbaf-140">繼續執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-140">Continue the install process.</span></span> <span data-ttu-id="dbbaf-141">您應該會發現服務密碼和憑證指紋已預先填入。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="dbbaf-142">如果不是，請在繼續之前先新增您儲存的值。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="dbbaf-143">開啟 [管理 PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="dbbaf-144">升級代理程式元件：</span><span class="sxs-lookup"><span data-stu-id="dbbaf-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="dbbaf-145">在執行腳本時，您應該會收到卸載舊版本產品的提示。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="dbbaf-146">答案是。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="dbbaf-147">繼續執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-147">Continue the install process.</span></span> <span data-ttu-id="dbbaf-148">您應注意到網站埠已經預先填入。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="dbbaf-149">如果不是，請在繼續之前先新增您儲存的值。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="dbbaf-150">使用瀏覽器驗證網站是否如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dbbaf-151">代理程式升級可以搭配-NoPrompt 參數使用。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="dbbaf-152">這可讓卸載/安裝程式以無訊息的方式執行，允許諸如 PSExec 之類的工具在大量的伺服器上遠端執行升級。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="dbbaf-153">手動升級</span><span class="sxs-lookup"><span data-stu-id="dbbaf-153">Manual upgrade</span></span>

<span data-ttu-id="dbbaf-154">若由於某些原因，自動升級會失敗，您可以無條件執行手動升級，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dbbaf-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="dbbaf-155">在監聽器電腦上，透過「程式和功能」控制台中的 [程式和功能] 控制台卸載監聽器、網站和代理程式 () 。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="dbbaf-156">保留 Redis，讓快取中的資料會透過升級程式進行維護。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="dbbaf-157">安裝新版本的元件，包括系統提示時所儲存的值。</span><span class="sxs-lookup"><span data-stu-id="dbbaf-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="dbbaf-158">如需安裝元件的詳細資訊，請參閱 [部署統計資料管理員](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="dbbaf-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="dbbaf-159">相關資訊</span><span class="sxs-lookup"><span data-stu-id="dbbaf-159">For more information</span></span>
<span data-ttu-id="dbbaf-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="dbbaf-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="dbbaf-161">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="dbbaf-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="dbbaf-162">商務用 Skype Server 統計資料的規劃</span><span class="sxs-lookup"><span data-stu-id="dbbaf-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="dbbaf-163">部署商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="dbbaf-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="dbbaf-164">疑難排解商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="dbbaf-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
