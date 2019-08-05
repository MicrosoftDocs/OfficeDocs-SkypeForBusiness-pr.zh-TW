---
title: 新增 Director 檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: 您必須指定檔案共用作為 Director 的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
ms.openlocfilehash: e3121502ddd3267cbaf11f82f1ee271279ec4d2c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193603"
---
# <a name="add-director-file-store"></a>新增 Director 檔案存放區

您必須指定檔案共用作為 Director 的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。

> [!IMPORTANT]
> 將 Director 新增至拓撲後，您需要有設定檔案存放區，以及在要作為檔案存放區的檔案共用上設定判別存取控制清單 (DACL) 所需的適當存取權限，才能發行拓撲。這表示，當您執行拓撲產生器和發行新的拓撲時，您必須已以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。

如需檔案共用的儲存支援的詳細資訊，請參閱支援文件中的〈[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)〉及部署文件中的〈[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)〉。如需檔案共用組合的詳細資訊，請參閱支援文件中的〈[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)〉。如需設計 Director 適用之拓撲的詳細資訊，請參閱部署文件中的〈[Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx)〉。


