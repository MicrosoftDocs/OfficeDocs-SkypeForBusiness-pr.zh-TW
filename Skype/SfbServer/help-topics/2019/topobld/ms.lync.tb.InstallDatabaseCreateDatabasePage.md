---
title: 安裝及建立資料庫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以選取要為部署建立的資料庫。 根據預設，會在定義的網站中已定義的 SQL Server 上建立資料庫，而且會根據您放置資料庫所在的 SQL Server，自動部署及設定資料庫檔案。
ms.openlocfilehash: 4d7a6e4f67dd6b97c8f5f837589af7b096da50b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835713"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="6d9cf-104">安裝及建立資料庫</span><span class="sxs-lookup"><span data-stu-id="6d9cf-104">Install and Create Databases</span></span>

<span data-ttu-id="6d9cf-105">您可以選取要為部署建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="6d9cf-106">根據預設，會在定義的網站中已定義的 SQL Server 上建立資料庫，而且會根據您放置資料庫所在的 SQL Server，自動部署及設定資料庫檔案。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="6d9cf-p103">**選取要建立的資料庫**：選取要部署及設定之任何資料庫的核取方塊。選取要部署之任何或所有資料庫的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="6d9cf-109">如果必須開啟任何) 和防火牆埠以容納要部署資料庫的實例，則必須已為實例設定 SQL Server (。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="6d9cf-110">如需詳細資訊，請參閱 [CONFIGURE SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="6d9cf-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="6d9cf-111">**Advanced**：按一下 sql server，然後按一下 [ **高級** ] 按鈕，為 SQL server 上的資料庫檔案位置選擇選項。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="6d9cf-112">如需進階資料庫檔案位置的詳細資訊，請參閱＜[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)＞</span><span class="sxs-lookup"><span data-stu-id="6d9cf-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="6d9cf-113">**上一步**：按一下此按鈕可回到上一個畫面 (根據您抵達此對話方塊的方式，有時可能無法使用)。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="6d9cf-114">**下一步**：按一下此按鈕可認可您在目前對話方塊上的選項，並前往下一個對話方塊以設定其他資訊</span><span class="sxs-lookup"><span data-stu-id="6d9cf-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="6d9cf-115">**取消**：按一下此按鈕可結束設定並捨棄變更。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="6d9cf-116">如果您想結束並捨棄變更，其中一些設定畫面 (並非所有設定畫面) 會出現提示。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="6d9cf-117">選取 **[是]** 會關閉目前的設定並關閉目前的設定，並傳回拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="6d9cf-118">選取 [否] 可回到目前的設定對話方塊，以供您繼續進行設定。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="6d9cf-119">**說明**：按一下 [說明] 按鈕可顯示與目前設定對話方塊相關的說明資訊。</span><span class="sxs-lookup"><span data-stu-id="6d9cf-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


