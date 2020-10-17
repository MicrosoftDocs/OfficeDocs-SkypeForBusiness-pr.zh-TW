---
title: Lync Server 2013：宣告應用程式的簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0bceaef7a165f4594d825a80b93ee167b68c85a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520810"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 的宣告應用程式概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

當您部署宣告應用程式時，您必須設定未指派的號碼表，以決定當某人撥打未指派的號碼時要採取的動作。 「未指派的號碼」表包含對組織有效的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。 當來電者撥打的電話號碼對您的組織而言是有效的，但是並未指派給任何人，Lync Server 會查詢未指派號碼路由表中的號碼，識別該號碼屬於哪一個範圍，並將通話路由傳送至該範圍所指定的宣告應用程式。 宣告應用程式會接聽來電，並 (如果將其設定為執行這項操作，則) 然後中斷通話，或將其轉接至預先決定的目的地，例如操作員。 您可以使用 Lync Server 管理命令介面 Cmdlet 來設定多個音訊訊息，或傳送目的地。

設定未指派號碼表的方式取決於其使用方式。如果您有不再使用的特定號碼，而且想要播放專為各個號碼而設計的訊息，則可以在未指派號碼表中輸入那些特定號碼。例如，如果您變更了客戶服務中心的號碼，則可以輸入舊的客戶服務號碼，並將其與宣告相關聯，以提供新號碼。如果您想要對撥打未指派之號碼的任何人 (如離職員工) 播放一般訊息，則可以輸入您組織中所有有效分機的範圍。只要來電者撥打目前未指派的號碼，就會叫用未指派號碼表。

在 Lync Server 2013 中，宣告應用程式會自動隨回應群組應用程式一起安裝。 宣告及回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，會自動部署這兩個應用程式。

</div>

<span> </span>

</div>

</div>

</div>

