---
title: Lync Server 2013： 使用 Office 自訂工具 (OCT)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55cfa8fd795feeca5e265f43823c4263512211f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Lync Server 2013 中使用 Office 自訂工具 (OCT)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

Office 自訂工具 (OCT) 屬於安裝程式的一部分，也是許多自訂的建議使用工具。 您可以使用 OCT 自訂 Office，並將自訂儲存在安裝程式自訂 .msp 檔案中。 您將此檔案放在網路安裝點上的 Updates 資料夾中。 當您安裝 Office 時，安裝程式會在 Updates 資料夾中尋找安裝程式自訂檔案，並套用自訂。 Updates 資料夾可以僅可用於 Office 2013 初始安裝期間部署軟體更新。

OCT 是安裝程式的一部分，且其隨附於大量授權版的產品。 您輸入執行 OCT`setup.exe /admin`在包含 Office 2013 的網路安裝點的根目錄從命令列的來源檔。 例如，使用下列程式碼：

`\\server\share\Office15\setup.exe /admin`

管理員使用 OCT 建立安裝程式自訂 .msp 檔案。 Microsoft Office 2010 OCT 中，如同系統管理員可以自訂下列區域：

  - **安裝程式**用於指定預設安裝位置上的用戶端和預設組織名稱、 其他網路安裝來源、 產品金鑰、 使用者授權合約、 顯示層級、 更早版本的 Office 中移除，請安裝、 安全性設定，以及安裝程式內容期間要執行自訂程式。

  - **功能**用來設定使用者設定及自訂如何安裝 Office 的功能。 系統管理員可以使用 OCT 來指定使用者的 Office 應用程式設定的初始的預設值。 使用者可以在安裝之後修改大部分的設定。

  - **其他內容**用來新增或移除檔案、 新增或移除登錄項目，以及設定捷徑。

  - **outlook**用於自訂使用者的預設 Outlook 設定檔、 指定 Exchange 設定、 新增帳戶、 移除帳戶和匯出設定，以及指定傳送\\接收群組。

如需 OCT 的詳細資訊，請參閱<https://go.microsoft.com/fwlink/p/?linkid=267516>。

</div>

<span> </span>

</div>

</div>

</div>

