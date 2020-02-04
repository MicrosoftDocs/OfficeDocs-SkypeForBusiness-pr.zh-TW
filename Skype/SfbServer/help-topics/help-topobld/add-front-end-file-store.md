---
title: 新增前端檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: 您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
ms.openlocfilehash: 3f613b38250e6d8e39bb0d9eb1d2981303163514
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685166"
---
# <a name="add-front-end-file-store"></a>新增前端檔案存放區

您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。

> [!IMPORTANT]
> 檔案共用不能位於 Enterprise Edition 前端伺服器，但可以位於 Standard Edition Server。

> [!IMPORTANT]
> 您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在您定義的位置中建立檔案共用，才能發行拓撲。

> [!IMPORTANT]
> 當您將 Enterprise 前端集區或 Standard Edition Server 新增至拓撲時，拓撲產生器在要作為檔案存放區的檔案共用上，必須能夠設定檔案存放區和設定判別存取控制清單 (DACL)。這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。

如需檔案共用的儲存支援的詳細資訊，請參閱支援文件中的〈[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)〉及部署文件中的〈[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)〉。如需檔案共用組合的詳細資訊，請參閱支援文件中的〈[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)〉。如需設計 Enterprise Edition 前端集區適用的拓撲之詳細資訊，請參閱部署文件中的〈[Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)〉。


