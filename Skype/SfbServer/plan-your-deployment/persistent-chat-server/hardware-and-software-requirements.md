---
title: 常設聊天室伺服器的硬體與軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '摘要: 請閱讀本主題, 瞭解商務用 Skype Server 2015 中持續聊天伺服器的硬體和軟體需求。'
ms.openlocfilehash: e700b76c8af29a0c877c1dc594244a299b8a3904
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194042"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="51bc0-103">常設聊天室伺服器的硬體與軟體需求</span><span class="sxs-lookup"><span data-stu-id="51bc0-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="51bc0-104">**摘要:** 若要瞭解商務用 Skype Server 2015 中持續聊天伺服器的硬體和軟體需求, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="51bc0-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="51bc0-105">永久聊天伺服器可以與商務用 Skype Server 2015 (企業版或標準版) 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="51bc0-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="51bc0-106">需求取決於您所安裝的商務用 Skype Server 2015 版本, 以及貴企業的效能需求。</span><span class="sxs-lookup"><span data-stu-id="51bc0-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="51bc0-107">企業版最多可支援80000個併發使用者;標準版版本最多可支援20000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="51bc0-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="51bc0-108">持續聊天是由前端元件以及後端 SQL 資料庫元件所組成。</span><span class="sxs-lookup"><span data-stu-id="51bc0-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="51bc0-109">在您部署持久聊天伺服器之前, 您必須確保符合下列硬體和軟體需求:</span><span class="sxs-lookup"><span data-stu-id="51bc0-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="51bc0-110">符合最低需求以支援商務用 Skype Server 2015、持續聊天伺服器、資料庫伺服器和檔案伺服器的硬體。</span><span class="sxs-lookup"><span data-stu-id="51bc0-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="51bc0-111">如需詳細資訊, 請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="51bc0-112">支援的作業系統和資料庫軟體。</span><span class="sxs-lookup"><span data-stu-id="51bc0-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="51bc0-113">如需支援的作業系統和資料庫軟體以及 Windows 更新需求的詳細資訊, 請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="51bc0-114">商務用 Skype Server 2015 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="51bc0-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="51bc0-115">前端伺服器是會話初始通訊協定 (SIP) 路由的基礎, 可讓執行持續聊天伺服器的電腦與持久的聊天功能都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="51bc0-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="51bc0-116">訊息佇列軟體。</span><span class="sxs-lookup"><span data-stu-id="51bc0-116">Message Queuing software.</span></span> <span data-ttu-id="51bc0-117">持續聊天伺服器和持續聊天相容性服務 (如果已部署) 使用。</span><span class="sxs-lookup"><span data-stu-id="51bc0-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="51bc0-118">下列各節說明持續性聊天伺服器和儲存持續聊天資料之資料庫的特定需求。</span><span class="sxs-lookup"><span data-stu-id="51bc0-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="51bc0-119">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="51bc0-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="51bc0-120">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="51bc0-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="51bc0-121">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="51bc0-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="51bc0-122">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="51bc0-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="51bc0-123">前端伺服器需求</span><span class="sxs-lookup"><span data-stu-id="51bc0-123">Front End Server requirements</span></span>

<span data-ttu-id="51bc0-124">前端伺服器需求取決於您是否要使用商務用 Skype Server 2015 (企業版或標準版) 部署持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="51bc0-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="51bc0-125">如果您要使用商務用 Skype Server 2015 (企業版) 部署持久聊天伺服器, 您可以在企業版池中的一或多台獨立電腦上部署持久聊天伺服器前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="51bc0-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="51bc0-126">您無法在商務用 Skype Server 2015 前端伺服器上 collocate 持續聊天前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="51bc0-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="51bc0-127">單一持續式聊天伺服器前端伺服器可以支援20000作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="51bc0-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="51bc0-128">您可以使用最多4個作用中端的持久聊天伺服器池, 從而支援總共80000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="51bc0-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="51bc0-129">如果您要部署與商務用 Skype Server 2015 標準版的持久聊天伺服器, 您可以 collocate 與前端伺服器的持續聊天。</span><span class="sxs-lookup"><span data-stu-id="51bc0-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="51bc0-130">這個單伺服器部署最多可支援20000個使用者。</span><span class="sxs-lookup"><span data-stu-id="51bc0-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="51bc0-131">持續聊天伺服器資料庫需求</span><span class="sxs-lookup"><span data-stu-id="51bc0-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="51bc0-132">持續聊天伺服器需要 SQL Server 資料庫軟體來儲存聊天室記錄及內容、設定資料、使用者預配資料, 以及其他相關的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="51bc0-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="51bc0-133">您也可以使用持續性聊天規範資料庫來儲存合規性資料。</span><span class="sxs-lookup"><span data-stu-id="51bc0-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="51bc0-134">持久聊天資料庫可以在相同的 SQL Server 上 collocated, 或甚至與後端資料庫一樣是相同的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="51bc0-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="51bc0-135">如果您要在商務用 Skype Server 2015 企業版中安裝持久聊天伺服器, 以確保最佳效能, 建議您安裝永久聊天檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="51bc0-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="51bc0-136">如果您要在商務用 Skype Server 2015 標準版中安裝持久聊天伺服器, 您可以在本機 SQL Server Express 實例上部署永久聊天存放後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="51bc0-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="51bc0-137">持久聊天資料庫 (mgc) 和規範資料庫 (mgccomp) 可位於相同的 SQL Server 實例或不同的 SQL 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="51bc0-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="51bc0-138">若要準備資料庫伺服器平臺, 請確定每個電腦都符合硬體需求, 然後再安裝必備軟體。</span><span class="sxs-lookup"><span data-stu-id="51bc0-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="51bc0-139">持續聊天資料庫伺服器的伺服器平臺需要與商務用 Skype Server 2015 後端資料庫伺服器相同的硬體。</span><span class="sxs-lookup"><span data-stu-id="51bc0-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="51bc0-140">如需詳細資訊, 請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="51bc0-141">在資料庫伺服器上, 請確定已安裝下列其中一個軟體應用程式:</span><span class="sxs-lookup"><span data-stu-id="51bc0-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="51bc0-142">Microsoft SQL Server 2017 (含最新 service pack)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="51bc0-143">Microsoft SQL Server 2016 Service Pack 1, 而且您必須在商務用 Skype Server 累積更新7或更新版本上執行。</span><span class="sxs-lookup"><span data-stu-id="51bc0-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="51bc0-144">我們建議您使用最新的 service pack 執行 SQL Server 2016。</span><span class="sxs-lookup"><span data-stu-id="51bc0-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="51bc0-145">如需有關如何安裝 Microsoft SQL Server 2016 的詳細資訊, 請參閱[安裝 SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="51bc0-146">Microsoft SQL Server 2014, 且您必須在商務用 Skype Server 累積更新6或更新版本上執行。</span><span class="sxs-lookup"><span data-stu-id="51bc0-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="51bc0-147">我們建議您使用最新的 service pack 執行 SQL Server 2014。</span><span class="sxs-lookup"><span data-stu-id="51bc0-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="51bc0-148">如需有關如何安裝 Microsoft SQL Server 2014 的詳細資訊, 請參閱[安裝 SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="51bc0-149">Microsoft SQL Server 2012 (64 位版本), 我們建議使用最新的 service pack 執行。</span><span class="sxs-lookup"><span data-stu-id="51bc0-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="51bc0-150">如需有關如何安裝 Microsoft SQL Server 2012 的詳細資訊, 請參閱[安裝 SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="51bc0-151">持續聊天伺服器憑證需求</span><span class="sxs-lookup"><span data-stu-id="51bc0-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="51bc0-152">如需取得證書、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊, 請參閱[部署商務用 Skype Server 2015](../../deploy/deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="51bc0-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="51bc0-153">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="51bc0-153">For more information</span></span>

<span data-ttu-id="51bc0-154">如需硬體和軟體需求的詳細資訊, 請參閱下列主題:</span><span class="sxs-lookup"><span data-stu-id="51bc0-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="51bc0-155">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="51bc0-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="51bc0-156">商務用 Skype Server 2015 的環境需求</span><span class="sxs-lookup"><span data-stu-id="51bc0-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

