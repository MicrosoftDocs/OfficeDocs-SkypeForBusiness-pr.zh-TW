---
title: 安裝及建立資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 選取您要為您的部署建立的資料庫。 根據預設，資料庫會在定義的網站中的定義 SQL 伺服器上建立，並將根據您要放置資料庫的 SQL Server，自動部署及設定資料庫檔案。
ms.openlocfilehash: 4bd69f1caa3322dbbf2d91a67caef54b72ece200
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793611"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="2d112-104">安裝及建立資料庫</span><span class="sxs-lookup"><span data-stu-id="2d112-104">Install and Create Databases</span></span>

<span data-ttu-id="2d112-105">選取您要為您的部署建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2d112-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="2d112-106">根據預設，資料庫會在定義的網站中的定義 SQL 伺服器上建立，並將根據您要放置資料庫的 SQL Server，自動部署及設定資料庫檔案。</span><span class="sxs-lookup"><span data-stu-id="2d112-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="2d112-107">**選取您要建立的資料庫**：選取您想要部署及設定的任何資料庫的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2d112-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="2d112-108">選取您將部署之任何或所有資料庫的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2d112-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="2d112-109">必須已針對實例（如果有的話）設定 SQL Server，而且必須開啟防火牆埠，才能容納您要部署資料庫的實例。</span><span class="sxs-lookup"><span data-stu-id="2d112-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="2d112-110">如需詳細資訊，請參閱[設定 SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="2d112-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="2d112-111">[**高級**]：按一下 sql Server，然後按一下 [**高級**] 按鈕，為您的 SQL server 上的資料庫檔案位置選擇選項。</span><span class="sxs-lookup"><span data-stu-id="2d112-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="2d112-112">如需高級資料庫檔案放置的詳細資料，請參閱[使用 Lync Server 管理命令介面的資料庫安裝](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="2d112-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="2d112-113">**返回**：按一下此按鈕會將您移至前一個畫面（可能不一定會顯示，視您在這個對話方塊中到達的方式而定）。</span><span class="sxs-lookup"><span data-stu-id="2d112-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="2d112-114">**下一步**：按一下此按鈕會在目前的對話方塊中提交您的選取範圍，並將您帶到下一個對話方塊來設定其他資訊</span><span class="sxs-lookup"><span data-stu-id="2d112-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="2d112-115">[**取消**]：按一下此按鈕將會結束設定並捨棄您所做的變更。</span><span class="sxs-lookup"><span data-stu-id="2d112-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="2d112-116">部分（但不是所有配置畫面）會在您想要結束並放棄變更時提示您。</span><span class="sxs-lookup"><span data-stu-id="2d112-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="2d112-117">選取 **[是]** 會關閉目前的設定並關閉目前的設定，並將您傳回拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="2d112-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="2d112-118">選取 [**否**] 會將您返回 [目前的設定] 對話方塊，並允許您繼續設定。</span><span class="sxs-lookup"><span data-stu-id="2d112-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="2d112-119">說明 **：按一下**[**說明**] 按鈕會顯示與 [目前設定] 對話方塊相關聯的說明資訊。</span><span class="sxs-lookup"><span data-stu-id="2d112-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


