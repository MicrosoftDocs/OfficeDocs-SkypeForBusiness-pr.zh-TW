---
title: Lync Server 2013： 部署 Lync 用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 351fc1b62f0ef72cb3580f3c5d43dc8486799aec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>部署 Lync Server 2013 中的 Lync 用戶端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

Lync 2013 引進了用戶端部署的不同方法。 從舊版不同，在 Lync 2013 就不再有它自己的安裝程式。 相反地，Lync 隨附於 Office 2013 安裝程式。 若要將 Lync 2013 部署到您的使用者，您可以使用 Office 2013 的安裝方式與自訂工具。

  - **Office 2013 Windows Installer**是 Windows installer 安裝套件，包含多個 MSI 檔案。 中性語言核心 MSI 套件結合了一或多個特定語言套件，組成完整的產品。 安裝程式組合了個別套件，在安裝 Office 於使用者的電腦期間 (以及之後)，執行自訂與維護工作。 本節中的主題說明如何使用和自訂 Office 2013 Windows 安裝程式，以部署 Lync 2013。

  - **Office 2013 隨-即**是會從 Microsoft Office 365 入口網站串流 Office 安裝程式檔案傳送給使用者的安裝程式。 管理員可以使用隨選即用的 Office 部署工具來自訂安裝。 由於 Office 2013 到隨主要用於 Microsoft Office 365 環境，本節中的詳細資料不說明此安裝方法。 使用 Office 2013 Resource Kit > 文件中使用和自訂按一下-隨選即用安裝的詳細的資訊。 系統管理員也可以下載至內部部署位置，也就是很有用，當您想要減少網路上的需求，或防止使用者從網際網路由於安裝軟體的 Office 2013 按一下-隨選即用程式及語言來源檔案公司安全性需求。

本節中的主題著重於如何使用 Office 2013 MSI 型安裝程式來部署用戶端。 您的主要參考應詳細說明如何準備您的基礎結構、 自訂安裝程式，並部署 Office 2013 Office 2013 Resource Kit > 文件。 不過，您應該使用本節各主題中，這是專屬於 Lync 2013 的部署考量註明搭配 Office 文件。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>線上會議增益集 for Lync 2013 支援 Outlook 訊息和共同作業用戶端內管理會議，與 Lync 2013 自動安裝。</P>
> <LI>
> <P>Office 2013 安裝程式不會解除安裝舊版的 Lync 或 Office Communicator。 Lync 2013 用戶端安裝並排顯示與其他 Lync 或 Office Communicator 用戶端</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [自訂 Lync Server 2013 中的用戶端安裝](lync-server-2013-customizing-client-installation.md)

  - [自訂 Lync 2010 和 Lync Server 2013 中的使用者介面](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [自訂的線上會議增益集在 Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)

  - [在 Lync Server 2013 中設定支援的用戶端版本](lync-server-2013-configuring-supported-client-versions.md)

  - [在 Lync Server 2013 中設定增強的目前狀態隱私權模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

