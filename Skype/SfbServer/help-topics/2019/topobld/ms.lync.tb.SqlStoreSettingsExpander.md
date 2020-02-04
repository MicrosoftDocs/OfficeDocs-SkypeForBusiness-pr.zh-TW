---
title: SQL 存放區設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯 SQL Server 資料庫的屬性，您必須變更 SQL Server 資料庫實例。 您無法使用 [編輯屬性] 對話方塊來執行工作，例如，將您的封存伺服器資料庫從一部電腦移到另一部。 此外，您無法使用 [編輯屬性] 對話方塊來變更託管中央管理儲存區的 SQL Server 實例。
ms.openlocfilehash: ccaa6d2ceedfdef3f180de93e763c28b7167d45a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701458"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="555e4-105">SQL 存放區設定展開工具</span><span class="sxs-lookup"><span data-stu-id="555e4-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="555e4-106">若要編輯 SQL Server 資料庫的屬性，您必須變更 SQL Server 資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="555e4-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="555e4-107">您無法使用 [**編輯屬性**] 對話方塊來執行工作，例如，將您的封存伺服器資料庫從一部電腦移到另一部。</span><span class="sxs-lookup"><span data-stu-id="555e4-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="555e4-108">此外，您無法使用 [**編輯屬性**] 對話方塊來變更託管中央管理儲存區的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="555e4-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="555e4-109">編輯 SQL Server 資料庫的屬性</span><span class="sxs-lookup"><span data-stu-id="555e4-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="555e4-110">若要變更由中央管理儲存體以外的任何資料庫所使用的 SQL Server 實例，請在拓撲建立器中完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="555e4-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="555e4-111">修改 SQL Server 實例</span><span class="sxs-lookup"><span data-stu-id="555e4-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="555e4-112">在 [ **SQL 店鋪**] 節點下選取適當的資料庫，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="555e4-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="555e4-113">在 [**編輯屬性**] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="555e4-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="555e4-114">若要使用預設的 SQL Server 實例，請選取 [**預設實例**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="555e4-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="555e4-115">若要使用命名資料庫實例，請選取 [**命名實例**]，在文字方塊中輸入實例名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="555e4-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="555e4-116">您應該只輸入實例名稱（例如，ArchivingInstance），而非整個 SQL Server 路徑。</span><span class="sxs-lookup"><span data-stu-id="555e4-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="555e4-117">當您在 [**編輯屬性**] 對話方塊中工作時，拓撲建立器不會確認您輸入的資料庫實例是有效的實例。</span><span class="sxs-lookup"><span data-stu-id="555e4-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="555e4-118">例如，如果您無意間 typeArchivingInstanec 為實例名稱，然後按一下 **[確定]**，拓撲建立器就會接受不正確實例。</span><span class="sxs-lookup"><span data-stu-id="555e4-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="555e4-119">您必須修正此錯誤，才能發佈此拓朴：如果找不到 SQL Server 實例，拓撲建立器就不會為您建立該實例。</span><span class="sxs-lookup"><span data-stu-id="555e4-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

