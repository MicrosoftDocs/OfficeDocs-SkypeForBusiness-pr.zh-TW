---
title: 新增前端檔案存放區
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: 您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
ms.openlocfilehash: 85e1e68c64e8175968211cccac83bcf6302cb5e0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844546"
---
# <a name="add-front-end-file-store"></a>新增前端檔案存放區

您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。

> [!IMPORTANT]
> 檔案共用不能位於 Enterprise Edition 前端伺服器上，但可以位於 Standard Edition 伺服器上。

> [!IMPORTANT]
> 您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在您定義的位置中建立檔案共用，才能發行拓撲。

> [!IMPORTANT]
> 當您將 Enterprise 前端集區或 Standard Edition Server 新增至拓撲時，拓撲產生器在要作為檔案存放區的檔案共用上，必須能夠設定檔案存放區和設定判別存取控制清單 (DACL)。這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。

如需檔案共用儲存支援的詳細資訊，請參閱支援檔中的檔案[儲存體支援](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)，以及部署檔中的[SQL Server 資料和記錄檔位置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。 如需檔案共用組合的詳細資訊，請參閱支援文件中的＜[Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)＞。 如需設計 Enterprise Edition 前端集區適用之拓撲的詳細資訊，請參閱部署文件中的＜[Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)＞ 。