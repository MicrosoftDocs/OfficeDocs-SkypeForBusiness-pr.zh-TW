---
title: Lync Server 2013：宣告應用程式所使用的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e4a0fdfe0dcdd69a3f371aed338caf7f73348
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的宣告應用程式所使用的元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

在 Lync Server 2013 中，宣告應用程式是回應群組應用程式的元件。 當您部署企業語音時，宣告應用程式會自動安裝並與回應群組應用程式一起啟用。 本節說明支援宣告應用程式的元件。

<div>

## <a name="announcement-application-components"></a>宣告應用程式元件

下列 Lync 伺服器元件支援宣告應用程式：

  - **應用程式服務**   應用程式服務提供部署、託管及管理整合通訊應用程式的平臺。 應用程式服務會自動安裝在前端池的每個前端伺服器上，以及每個標準版伺服器上。

  - **回應群組應用**   程式：回應群組應用程式是由應用程式服務託管的其中一個整合通訊應用程式。 當未指派的電話號碼範圍設定為傳送給宣告時，必須使用回應群組申請，才能傳送電話號碼所撥的通話。 （如果所有範圍都設定為路由到 Exchange 整合通訊（UM），則不需要回應群組應用程式。

  - **音訊**檔案是用來進行宣告的。   

  - **檔案存放**   ：宣告應用程式會使用檔案存放區來儲存其音訊檔案。

  - **Lync server [控制台**   ] 您可以使用 lync server [控制台] 來設定 [未指定的數位] 資料表。

  - **Lync server 管理命令**   介面：您可以使用 lync server 管理命令介面 Cmdlet 來設定宣告設定和未指定的數位資料表。

</div>

</div>

<span> </span>

</div>

</div>

</div>

