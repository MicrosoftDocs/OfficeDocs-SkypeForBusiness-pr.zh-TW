---
title: 新增封存伺服器檔案存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: 若要同時啟用立即訊息 (IM) 和 web 會議 (會議) 內容，您必須指定要做為檔案存放區的檔案共用，以供所有 web 會議內容的副本使用。 您可以使用封存檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。
ms.openlocfilehash: 2e8c4ac23ce68eab111bbb7775eec23aba2f12d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100229"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="1f28d-104">新增封存伺服器檔案存放區</span><span class="sxs-lookup"><span data-stu-id="1f28d-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="1f28d-105">若要同時啟用立即訊息 (IM) 和 web 會議 (會議) 內容，您必須指定要做為檔案存放區的檔案共用，以供所有 web 會議內容的副本使用。</span><span class="sxs-lookup"><span data-stu-id="1f28d-105">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content.</span></span> <span data-ttu-id="1f28d-106">您可以使用封存檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="1f28d-106">You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f28d-107">您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在已定義的位置中建立檔案共用，才能發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="1f28d-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="1f28d-108">> 當您將封存伺服器新增至拓撲時，拓撲產生器必須能夠設定封存檔案存放區，並設定檔案共用上 (Dacl) 上的自由存取控制清單，以用於檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="1f28d-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="1f28d-109">這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="1f28d-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="1f28d-110">如需檔案共用儲存支援的詳細資訊，請參閱部署檔中的支援檔和[SQL Server 資料和記錄檔位置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)的檔案[儲存支援](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)。</span><span class="sxs-lookup"><span data-stu-id="1f28d-110">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="1f28d-111">如需檔案共用組合的詳細資訊，請參閱支援文件中的＜[Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)＞。</span><span class="sxs-lookup"><span data-stu-id="1f28d-111">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span>