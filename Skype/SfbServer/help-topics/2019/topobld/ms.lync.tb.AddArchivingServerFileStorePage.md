---
title: 新增封存伺服器檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: 若要啟用立即訊息 (IM) 和 Web 會議內容的封存，您必須指定檔案共用來作為檔案存放區，以存放所有 Web 會議內容的複本。您可以使用現有的檔案共用作為封存檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
ms.openlocfilehash: 568d7254b4af28271befcf51811ff3659780fe3f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689698"
---
# <a name="add-archiving-server-file-store"></a>新增封存伺服器檔案存放區

若要啟用立即訊息 (IM) 和 Web 會議內容的封存，您必須指定檔案共用來作為檔案存放區，以存放所有 Web 會議內容的複本。您可以使用現有的檔案共用作為封存檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。

> [!IMPORTANT]
> 您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在已定義的位置中建立檔案共用，才能發行拓撲。 > 當您在拓撲中新增封存伺服器時，拓撲建立器必須能夠設定封存檔案存放區，並設定檔案共用上的隨機存取控制清單（Dacl），以用於檔案存放區。 這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。

如需詳細瞭解檔案共用的儲存支援，請參閱支援文件中的〈[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)〉，以及部署文件中的〈[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)〉。如需詳細瞭解檔案共用的組合，請參閱支援文件中的〈[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)〉。


