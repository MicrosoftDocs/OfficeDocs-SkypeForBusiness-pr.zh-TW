---
title: 新增前端檔案存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: 您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
ms.openlocfilehash: 66289799ba69fee037d2dbe465be78cf7d77be67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824113"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="fb2fa-104">新增前端檔案存放區</span><span class="sxs-lookup"><span data-stu-id="fb2fa-104">Add Front End File Store</span></span>

<span data-ttu-id="fb2fa-p102">您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb2fa-107">檔案共用不能位於 Enterprise Edition 前端伺服器，但可以位於 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb2fa-108">您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在您定義的位置中建立檔案共用，才能發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb2fa-p103">當您將 Enterprise 前端集區或 Standard Edition Server 新增至拓撲時，拓撲產生器在要作為檔案存放區的檔案共用上，必須能夠設定檔案存放區和設定判別存取控制清單 (DACL)。這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="fb2fa-111">如需檔案共用儲存支援的詳細資訊，請參閱部署檔中的支援檔和[SQL Server 資料和記錄檔位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)的檔案[儲存支援](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-111">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="fb2fa-112">如需檔案共用組合的詳細資訊，請參閱支援文件中的＜[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-112">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="fb2fa-113">如需設計 Enterprise Edition 前端集區適用之拓撲的詳細資訊，請參閱部署文件中的＜[Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)＞ 。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>


