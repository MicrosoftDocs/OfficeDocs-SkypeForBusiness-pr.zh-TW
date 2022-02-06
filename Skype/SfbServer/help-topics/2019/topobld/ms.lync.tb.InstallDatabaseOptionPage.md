---
title: 安裝資料庫選項頁面
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 您可以設定在 SQL Server 上放置資料庫及記錄檔的高級選項。 可用選項包括：
---

# <a name="install-database-options-page"></a>安裝資料庫選項頁面

您可以設定在 SQL Server 上放置資料庫及記錄檔的高級選項。 可用選項包括：

> [!IMPORTANT]
> 選取最符合您的需求和原則的選項，與您的 SQL Server 電腦上的資料和記錄檔位置有關。

 **自動判斷資料庫檔案位置**： [預設] 選項使用的演算法決定 SQL Server 上可用的空間，並分散資料庫及記錄檔以取得最佳效能。

 **使用 SQL Server 實例預設值**：選取此選項可根據 SQL Server 的實例設定，將資料庫檔案及記錄檔放入。 選項通常是由資料庫管理員管理及設定。

 **在目標 SQL Server 上這些路徑**：選取此選項可透過輸入存放資料庫及記錄檔之磁片磁碟機和資料夾的完整路徑，以定義您自己的 SQL Server 資料庫及記錄檔路徑。

> [!IMPORTANT]
> 您輸入的路徑可能會根據安裝中的效能優化演算法進行修改。 如需詳細資訊，請參閱 [使用 Lync Server 管理命令介面進行資料庫安裝](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)。

 **確定**：按一下 [確定] 按鈕認可您的變更。

 **取消**：按一下 [取消] 捨棄所有變更，並回到 [安裝資料庫] 畫面。

 說明 **：按一下**[說明] 按鈕，存取此說明頁面。

## <a name="see-also"></a>另請參閱

[SQL Server 資料和記錄檔位置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)