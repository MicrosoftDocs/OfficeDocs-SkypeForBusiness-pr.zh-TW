---
title: Lync Server 2013：部署 Lync 用戶端
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
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync 用戶端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Lync 2013 為用戶端部署帶來了不同的方法。 從先前的版本出發，Lync 2013 不再有自己的安裝程式。 相反地，Lync 隨附于 Office 2013 安裝程式。 若要將 Lync 2013 部署至您的使用者，您可以使用 Office 2013 安裝方法和自訂工具。

  - **Office 2013 Windows 安裝程式**是一個以 Windows 安裝程式為基礎的安裝套件，由多個 MSI 檔案組成。 語言中立的核心 MSI 套件與一或多個語言特定套件結合，以製作完整的產品。 安裝程式會彙編個別套件，並在安裝使用者電腦上的 Office 期間和之後執行自訂及維護作業。 本節中的主題說明如何使用及自訂 Office 2013 Windows 安裝程式來部署 Lync 2013。

  - **Office 2013** [隨選即用] 是從 Microsoft office 365 入口網站將 Office 設定檔案流向使用者的安裝程式。 系統管理員可以使用 Office 部署工具進行「隨選即用」來自訂安裝。 因為 Office 2013 隨選即用主要是在 Microsoft Office 365 環境中使用，所以本節不詳細說明此安裝方法。 有關使用及自訂「隨選即用」安裝的詳細資訊，請參閱 Office 2013 資源套件檔。 系統管理員也可以將 Office 2013 隨選即用程式及語言來源檔案下載到內部部署位置，這在您想要將網路上的需求最小化或防止使用者從網際網路安裝軟體時很有用。公司安全性需求。

本節中的主題將重點放在如何使用 Office 2013 MSI 安裝程式部署用戶端。 您的主要參考應該是 Office 2013 資源套件檔，其中詳細說明如何準備您的基礎結構、自訂安裝程式，以及部署 Office 2013。 不過，您應該將 Office 檔與本節中的主題搭配使用，以指出 Lync 2013 專用的部署考慮。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Lync 2013 的線上會議增益集（支援 Outlook 訊息和共同作業用戶端中的會議管理）會自動使用 Lync 2013 進行安裝。</P>
> <LI>
> <P>Office 2013 安裝程式不會卸載舊版的 Lync 或 Office Communicator。 Lync 2013 用戶端與其他 Lync 或 Office Communicator 用戶端並排安裝</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中自訂用戶端安裝](lync-server-2013-customizing-client-installation.md)

  - [在 Lync Server 2013 中自訂 Lync 行為和使用者介面](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [在 Lync Server 2013 中自訂線上會議增益集](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [在 Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)

  - [在 Lync Server 2013 中設定支援的用戶端版本](lync-server-2013-configuring-supported-client-versions.md)

  - [在 Lync Server 2013 中設定增強的目前狀態隱私權模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

