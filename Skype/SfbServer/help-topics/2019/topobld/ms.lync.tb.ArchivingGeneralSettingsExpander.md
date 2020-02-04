---
title: 封存伺服器一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 在拓撲產生器中，您可以編輯執行封存之個別伺服器的內容，方法是在主控台樹狀目錄中執行封存的伺服器上按右鍵，然後按一下工具列中的 [動作]，或是按一下 [動作] 窗格中的工作，再按一下 [編輯內容] 並變更下列任一選項：
ms.openlocfilehash: 6747db6d90fa3a27bd1ad52df2fb7e9177bd56f9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688856"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="93ff0-103">封存伺服器一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="93ff0-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="93ff0-104">在拓撲產生器中，您可以編輯執行封存之個別伺服器的內容，方法是在主控台樹狀目錄中執行封存的伺服器上按右鍵，然後按一下工具列中的 [動作]\*\*\*\*，或是按一下 [動作] 窗格中的工作，再按一下 [編輯內容] \*\*\*\* 並變更下列任一選項：</span><span class="sxs-lookup"><span data-stu-id="93ff0-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="93ff0-105">**FQDN**，以變更您要部署為執行封存之伺服器的原有伺服器完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="93ff0-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="93ff0-p101">**SQL 存放區**，以變更要用作封存 SQL Server 資料庫的 SQL Server 執行個體。如果您變更執行封存之伺服器的 SQL Server 資料庫，必須重新啟動執行封存的伺服器以確保變更生效。</span><span class="sxs-lookup"><span data-stu-id="93ff0-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="93ff0-p102">**檔案共用**，以變更要用作封存檔案存放區的資料夾。如果您變更執行封存之伺服器的檔案共用，必須重新啟動執行封存的伺服器以確保變更生效。此外，您必須將先前的會議檔案移至新的檔案存放區資料夾以避免遺失封存的會議檔案。</span><span class="sxs-lookup"><span data-stu-id="93ff0-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="93ff0-111">若要變更與執行封存之伺服器關聯的集區，請針對目前與執行封存之伺服器關聯的個別前端集區節點或 Survivable Branch Appliance 節點，選取 [編輯內容]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="93ff0-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93ff0-p103">如果您先前已在拓撲產生器中將執行封存的伺服器新增至拓撲，則 [封存] 節點會包含執行封存的伺服器。您可以編輯清單中的任何一部執行封存的伺服器內容。不過，除非您也已安裝執行封存之伺服器的服務，否則無法封存立即訊息或 Web 會議 (訊息)。</span><span class="sxs-lookup"><span data-stu-id="93ff0-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

