---
title: 新增封存伺服器檔案存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: 若要同時啟用立即訊息 (IM) 和 web 會議 (會議) 內容，您必須指定要做為檔案存放區的檔案共用，以供所有 web 會議內容的副本使用。 您可以使用封存檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。
ms.openlocfilehash: 99330997216ae9b36429cef59ef7dadfd7fe991a36924f62c23d7f4feeae3bbc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302577"
---
# <a name="add-archiving-server-file-store"></a>新增封存伺服器檔案存放區

若要同時啟用立即訊息 (IM) 和 web 會議 (會議) 內容，您必須指定要做為檔案存放區的檔案共用，以供所有 web 會議內容的副本使用。 您可以使用封存檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。

> [!IMPORTANT]
> 您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在已定義的位置中建立檔案共用，才能發行拓撲。 > 當您將封存伺服器新增至拓撲時，拓撲產生器必須能夠設定封存檔案存放區，並設定檔案共用上 (Dacl) 上的自由存取控制清單，以用於檔案存放區。 這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。

如需檔案共用儲存支援的詳細資訊，請參閱支援檔中的檔案[儲存體支援](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)，以及部署檔中的[SQL Server 資料和記錄檔位置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。 如需檔案共用組合的詳細資訊，請參閱支援文件中的＜[Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)＞。