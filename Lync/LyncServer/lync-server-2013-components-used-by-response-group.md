---
title: Lync Server 2013：回應群組使用的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Lync Server 2013 中回應群組使用的元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

當您部署企業語音時，系統會自動啟用回應群組應用程式。 本節將說明支援回應群組應用程式的元件。

<div>

## <a name="response-group-components"></a>回應群組元件

下列 Microsoft Lync Server 2013 元件支援回應群組應用程式：

  - **應用程式服務**   應用程式服務提供部署、託管及管理整合通訊應用程式（例如回應群組）的平臺。 應用程式服務會自動安裝在前端池的每個前端伺服器上，以及每個標準版伺服器上。

  - **回應群組應用**   程式：回應群組應用程式是由應用程式服務託管的其中一個整合通訊應用程式。 當您部署回應群組時，系統會自動包含此檔案。 回應群組應用程式會將來電路由及佇列傳送給代理群組。

  - **語言套件**   需要語言套件才能支援文字轉換語音和語音辨識。 當您設定郵件時，會使用這些語音技術，例如歡迎訊息及其他提示，以及互動式語音回應（IVR）問題與解答。 根據預設，當您部署 Lync Server 2013 時，會安裝26個支援的語言套件。

  - **音訊**檔案是用於郵件和等候音樂。   

  - ****    [檔案存放] 回應群組使用 [檔案存放區] 儲存音訊檔案。 多個回應群組池可以使用相同的檔案存放區實例。

  - **[回應群組**   設定] 工具： [回應群組設定] 工具是用來建立及設定回應群組的 web 型工具。 當您安裝 Web 服務時，系統會隨附 [回應群組設定] 工具。

  - **Microsoft lync server 2013 [控制台**   ] 您可以使用 Lync server [控制台] 來設定及設定回應群組的代理程式群組和佇列。

  - **Lync server 管理命令**   介面：您可以使用 Lync server 管理命令介面 Cmdlet 來設定所有回應群組設定。

  - **Microsoft Lync 2013**   正式代理（需要登入群組才能接受群組呼叫的工程師），請使用 Lync 2013 登入群組並登出。 如果為正式代理程式設定了代理群組，則代理程式會按一下 Lync 2013 中的功能表項目來開啟 Internet Explorer，並顯示可登入和登出群組的網頁主控台。

  - ****    在回應群組設定工具、代理程式的登入和登出主控台、Lync Server 控制台及回應群組用戶端 Web 服務中，都需要 web services web 服務。

  - **回應群組用戶端 web 服務**   回應群組應用程式會提供用戶端 web 服務，這可以由協力廠商應用程式用來取得代理程式、代理群組成員資格、代理登入狀態的相關資訊、呼叫群組的狀態，以及支援匿名呼叫的群組。 Lync 2013 和 Lync 2010 的人員使用回應群組用戶端 Web 服務來取得回應群組清單，讓代理程式可以用來進行匿名通話。 當您安裝 Web 服務時，會包含用戶端 web 服務。

</div>

</div>

<span> </span>

</div>

</div>

</div>

