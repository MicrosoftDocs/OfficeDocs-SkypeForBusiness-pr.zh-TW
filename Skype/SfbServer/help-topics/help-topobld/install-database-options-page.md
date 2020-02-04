---
title: 安裝資料庫選項頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 您可以在 SQL Server 上設定資料庫與記錄檔案位置的高級選項。 可用的選項包括：
ms.openlocfilehash: 0abcf0be4c6e7a4d808a7abaaad713c1b35cd37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697198"
---
# <a name="install-database-options-page"></a>安裝資料庫選項頁面

您可以在 SQL Server 上設定資料庫與記錄檔案位置的高級選項。 可用的選項包括：

> [!IMPORTANT]
> 選取最符合您的需求與原則的選項，這些選項與您的 SQL Server 電腦上的資料和記錄檔案位置有關。

 **自動判斷資料庫檔案位置**： [預設] 選項使用的演算法決定 SQL Server 上可用的空間，並散發資料庫與記錄檔以獲得最佳效能。

 **使用 Sql server 實例預設值**：選取此選項以根據 SQL Server 上的實例設定，放置資料庫檔案和記錄檔案。 選項通常是由資料庫管理員進行管理和設定。

 **我們在目標 SQL server 上的這些路徑**：選取這個選項，即可定義您自己的 SQL Server 資料庫路徑和記錄檔案，方法是輸入要放置資料庫及記錄檔的磁片磁碟機及資料夾的完整路徑。

> [!IMPORTANT]
> 您輸入的路徑可能會根據安裝中的效能優化演算法進行修改。 如需詳細資訊，請參閱[使用 Lync Server 管理命令介面的資料庫安裝](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)。

 **[確定]**：按一下 [確定] 按鈕，確認您的變更。

 [**取消**]：按一下 [取消] 放棄任何變更，然後返回 [安裝資料庫] 畫面。

 說明 **：按一下**[說明] 按鈕即可存取此說明頁面。

## <a name="see-also"></a>另請參閱

[SQL Server 資料與記錄檔的位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
