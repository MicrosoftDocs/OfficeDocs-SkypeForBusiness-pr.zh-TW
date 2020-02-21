---
title: 回應群組所使用的 Lync Server 2013： 元件
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
ms.openlocfilehash: 9bfefeabc1c9f64a4f1bf9fa794b269fbdcb0650
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Lync Server 2013 中的回應群組所使用的元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-11_

當您部署企業語音時，會自動啟用回應群組應用程式。 本節說明支援的回應群組應用程式的元件。

<div>

## <a name="response-group-components"></a>回應群組元件

回應群組應用程式支援下列的 Microsoft Lync Server 2013 元件：

  - **應用程式服務**   應用程式服務提供的平台的部署，裝載，及管理整合通訊應用程式，例如回應群組。 在每個前端伺服器上的前端集區中，每個 Standard Edition server 上，會自動安裝的應用程式服務。

  - **回應群組應用程式**   回應群組應用程式是下列其中一個裝載的應用程式服務的整合的通訊應用程式。 自動部署回應群組時，它是包含。 回應群組應用程式的路由和佇列的來電給代理群組。

  - **語言套件**   語言套件，才能支援文字轉語音和語音辨識。 在您設定訊息 (如歡迎訊息與其他提示) 以及互動式語音回應 (IVR) 的問題與回答時，都會用到這些語音技術。 依預設，26 支援部署 Lync Server 2013 安裝套件的語言。

  - **音訊檔案**   音訊檔可用於訊息和音樂。

  - **檔案存放區**   回應群組使用的檔案存放區儲存音訊檔案。 多個回應群組集區可以使用相同的檔案存放區的執行個體。

  - **回應群組組態工具**   回應群組組態工具是用來建立和設定回應群組的 web 式工具。 當您安裝 Web 服務包含回應群組組態工具。

  - **Microsoft Lync Server 2013 控制台**   您可以使用 Lync Server 控制台來安裝及設定代理群組以及回應群組的佇列。

  - **Lync Server 管理命令介面**   可以使用 Lync Server 管理命令介面 cmdlet 來設定所有回應群組設定。

  - **Microsoft Lync 2013**   正式代理 （給需要登入群組他們可以接受來電的群組之前） 使用 Lync 2013 登入和登出群組。 如果專員群組設定為正式代理程式時，代理程式按一下 [Lync 2013 開啟 Internet Explorer，並顯示出群組簽章的網頁主控台中的功能表項目。

  - **Web 服務**   Web 服務所需的回應群組組態工具、 代理的登入與登出主控台、 Lync Server Control Panel，以及回應群組用戶端 web 服務。

  - **回應群組用戶端 Web 服務**   回應群組應用程式提供用戶端 web 服務、 協力廠商應用程式可以用來擷取代理程式、 代理程式群組成員資格、 代理程式登入狀態、 群組、 通話狀態及支援匿名通話群組的相關資訊。 Lync 2013 和 Lync 2010 Attendant 可用於回應群組用戶端 Web 服務擷取的回應群組代理程式可以用來進行匿名呼叫清單。 用戶端 Web 服務會在您安裝 Web 服務時納入。

</div>

</div>

<span> </span>

</div>

</div>

</div>

