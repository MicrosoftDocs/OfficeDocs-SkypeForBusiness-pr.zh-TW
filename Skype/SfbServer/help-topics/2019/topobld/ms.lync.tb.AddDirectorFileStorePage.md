---
title: 新增 Director 檔案存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: 您必須指定用作 Director 之檔案存放區的檔案共用。 您可以使用檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。
ms.openlocfilehash: f134d561a948dbdb89ce655d59e5d5fc205bcbf4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811883"
---
# <a name="add-director-file-store"></a><span data-ttu-id="0478b-104">新增 Director 檔案存放區</span><span class="sxs-lookup"><span data-stu-id="0478b-104">Add Director File Store</span></span>

<span data-ttu-id="0478b-105">您必須指定用作 Director 之檔案存放區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="0478b-105">You must specify a file share to be used as the file store for Directors.</span></span> <span data-ttu-id="0478b-106">您可以使用檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="0478b-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0478b-p103">將 Director 新增至拓撲後，您需要有設定檔案存放區，以及在要作為檔案存放區的檔案共用上設定判別存取控制清單 (DACL) 所需的適當存取權限，才能發行拓撲。這表示，當您執行拓撲產生器和發行新的拓撲時，您必須已以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="0478b-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="0478b-109">如需檔案共用儲存支援的詳細資訊，請參閱部署檔中的支援檔和[SQL Server 資料和記錄檔位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)的檔案[儲存支援](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0478b-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="0478b-110">如需檔案共用組合的詳細資訊，請參閱支援文件中的＜[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="0478b-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="0478b-111">如需針對 Director 設計拓撲的詳細資訊，請參閱部署檔中的在拓撲產生器中 [定義單一 Director](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="0478b-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


