---
title: 新增封存伺服器檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: 若要啟用立即訊息 (IM) 和 Web 會議內容的封存，您必須指定檔案共用來作為檔案存放區，以存放所有 Web 會議內容的複本。您可以使用現有的檔案共用作為封存檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
ms.openlocfilehash: 4d8f14ec4cd4e63f7c1c48beb57cc2edbf6a56b2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821295"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="33b61-104">新增封存伺服器檔案存放區</span><span class="sxs-lookup"><span data-stu-id="33b61-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="33b61-p102">若要啟用立即訊息 (IM) 和 Web 會議內容的封存，您必須指定檔案共用來作為檔案存放區，以存放所有 Web 會議內容的複本。您可以使用現有的檔案共用作為封存檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="33b61-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33b61-107">您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在已定義的位置中建立檔案共用，才能發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="33b61-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="33b61-108">> 當您在拓撲中新增封存伺服器時，拓撲建立器必須能夠設定封存檔案存放區，並設定檔案共用上的隨機存取控制清單（Dacl），以用於檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="33b61-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="33b61-109">這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="33b61-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="33b61-p104">如需詳細瞭解檔案共用的儲存支援，請參閱支援文件中的〈[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)〉，以及部署文件中的〈[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)〉。如需詳細瞭解檔案共用的組合，請參閱支援文件中的〈[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="33b61-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


