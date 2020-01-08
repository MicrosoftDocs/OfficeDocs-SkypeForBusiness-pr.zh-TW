---
title: Lync Server 2013：環境測試的問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed158c598b9dc5596df23cb845f0adac4c6fed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Lync Server 2013 中的環境測試問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

最佳做法分析程式提供一種驗證 Lync Server 2013 環境是否支援設定的方式。 在 Active Directory 網域服務檢查中，最佳做法分析程式會執行下列動作：

  - 驗證 Active Directory 網域服務林及架構準備。

  - 識別部署中 Active Directory 網域服務網站和網域的數目。

  - 檢查目錄林及網域層級。

  - 檢查網網域控制站版本。

  - 識別網域、配置和架構命名內容。

  - 標識已啟用的使用者數目。

  - 檢查全域 Active Directory 網域服務設定的儲存位置。

  - 檢查 Lync Server 的服務連接點（SCPs）。

  - 識別資料庫版本。

<div>

## <a name="resolving-issues-with-the-environment"></a>解決環境問題

如果環境測試發現您的環境有問題，這些問題可能是由您的 Active Directory 設定或特定伺服器上執行的軟體層級問題所造成。 例如，如果最佳做法分析程式發現您環境中執行 Windows Server 2000 的任何網網域控制站，都會發出警告，而且您必須將這些網網域控制站升級為受支援版本的 Windows Server。

</div>

</div>

<span> </span>

</div>

</div>

</div>

