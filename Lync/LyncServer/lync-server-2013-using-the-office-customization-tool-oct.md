---
title: Lync Server 2013：使用 Office 自訂工具（OCT）
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
ms.openlocfilehash: b82db655a0b55858de9cdc32efd1a3f110247b54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Office 自訂工具（OCT）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Office 自訂工具（OCT）是安裝程式的一部分，且是許多自訂的建議工具。 使用 OCT，您可以自訂 Office，並在安裝程式自訂 .msp 檔案中儲存您的自訂專案。 您將檔案放在網路安裝點的 [更新] 資料夾中。 當您安裝 Office 時，安裝程式會在 [更新] 資料夾中尋找安裝程式自訂檔案，並套用自訂專案。 [更新] 資料夾只能用來在初次安裝 Office 2013 期間部署軟體更新。

OCT 是設定的一部分，且包含在產品的大量授權版本中。 您可以從包含 Office 2013 `setup.exe /admin`來源檔案之網路安裝點的根目錄，在命令列上輸入，以執行 OCT。 例如，請使用下列程式：

`\\server\share\Office15\setup.exe /admin`

系統管理員使用 OCT 來建立安裝程式自訂 .msp 檔案。 就像 Microsoft Office 2010 年10月一樣，管理員可以自訂下欄區域：

  - **設定**用來指定用戶端和預設組織名稱、其他網路安裝來源、產品金鑰、使用者授權合約、顯示階層、舊版 Office 的預設安裝位置、要在安裝期間執行的自訂程式、安全性設定和安裝屬性。

  - **功能**用來設定使用者設定，並自訂 Office 功能的安裝方式。 系統管理員可以使用 OCT 為使用者指定 Office 應用程式設定的初始預設值。 使用者可以在安裝之後修改大部分的設定。

  - **其他內容**用來新增或移除檔案、新增或移除登錄機碼目，以及設定快速鍵。

  - **Outlook**用來自訂使用者的預設 Outlook 設定檔、指定 Exchange 設定、新增帳戶、移除帳戶和匯出設定，以及指定\\傳送接收群組。

如需 OCT 的相關資訊， <http://go.microsoft.com/fwlink/p/?linkid=267516>請參閱。

</div>

<span> </span>

</div>

</div>

</div>

