---
title: 新增 Director 檔案存放區
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: 您必須指定用作 Director 之檔案存放區的檔案共用。 您可以使用檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。
ms.openlocfilehash: 47ff804eec897d1bf54dd2d012b777b022cd515e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400927"
---
# <a name="add-director-file-store"></a>新增 Director 檔案存放區

您必須指定用作 Director 之檔案存放區的檔案共用。 您可以使用檔案存放區的現有檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。

> [!IMPORTANT]
> 將 Director 新增至拓撲後，您需要有設定檔案存放區，以及在要作為檔案存放區的檔案共用上設定判別存取控制清單 (DACL) 所需的適當存取權限，才能發行拓撲。這表示，當您執行拓撲產生器和發行新的拓撲時，您必須已以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。

如需檔案共用儲存支援的詳細資訊，請參閱支援檔中的檔案[儲存體支援](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)，以及部署檔中的[SQL Server 資料和記錄檔位置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。 如需檔案共用組合的詳細資訊，請參閱支援文件中的＜[Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)＞。 如需針對 Director 設計拓撲的詳細資訊，請參閱部署檔中的在拓撲產生器中 [定義單一 Director](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) 。