---
title: 安裝及建立資料庫
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 您可以選取要為部署建立的資料庫。 根據預設，會在定義的網站的定義的 SQL Server 上建立資料庫，並根據您放置資料庫所在的 SQL Server 自動部署及設定資料庫檔案。
ms.openlocfilehash: 8cbb1fe545c83e5a76e38e9425ceb1c0418829a8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830127"
---
# <a name="install-and-create-databases"></a>安裝及建立資料庫

您可以選取要為部署建立的資料庫。 根據預設，會在定義的網站的定義的 SQL Server 上建立資料庫，並根據您放置資料庫所在的 SQL Server 自動部署及設定資料庫檔案。

 **選取要建立的資料庫**：選取要部署及設定之任何資料庫的核取方塊。選取要部署之任何或所有資料庫的核取方塊。

> [!CAUTION]
> 您必須已為實例 (設定 SQL Server，如果必須開啟任何) 和防火牆埠才能容納要部署資料庫的實例。 如需詳細資訊，請參閱＜[Configure SQL Server for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)＞

 **Advanced**：按一下 SQL Server，然後按一下 [**高級**] 按鈕，選擇您 SQL Server 上的資料庫檔案位置選項。 如需進階資料庫檔案位置的詳細資訊，請參閱＜[Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)＞

 **上一步**：按一下此按鈕可回到上一個畫面 (根據您抵達此對話方塊的方式，有時可能無法使用)。

 **下一步**：按一下此按鈕可認可您在目前對話方塊上的選項，並前往下一個對話方塊以設定其他資訊

 **取消**：按一下此按鈕可結束設定並捨棄變更。 如果您想結束並捨棄變更，其中一些設定畫面 (並非所有設定畫面) 會出現提示。 選取 **[是]** 會關閉目前的設定並關閉目前的設定，並傳回拓撲產生器。 選取 [否] 可回到目前的設定對話方塊，以供您繼續進行設定。

 **說明**：按一下 [說明] 按鈕可顯示與目前設定對話方塊相關的說明資訊。