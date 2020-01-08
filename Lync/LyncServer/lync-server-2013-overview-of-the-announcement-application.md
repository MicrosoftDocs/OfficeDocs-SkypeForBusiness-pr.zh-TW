---
title: Lync Server 2013：宣告應用程式簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e9cedddf6dfdf714bb3d0eef0e0cd01063b89f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的宣告應用程式概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

當您部署宣告應用程式時，您必須設定 [未指定的數位] 資料表，決定當有人撥打未指派的號碼時所採取的動作。 [未指定的數位] 表格包含適用于組織的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。 當來電者撥打電話給您的組織而言，但未指派給任何人時，Lync Server 會在未指定的數位路由表中查詢該號碼，找出該數位的範圍，並將呼叫路由到宣告為該範圍指定的應用程式。 [宣告] 應用程式會應答通話並播放音訊訊息（如果您將它設定為這樣做），然後中斷通話，或將它轉移至預先確定的目的地，例如操作員。 您可以使用 Lync Server 管理命令介面 Cmdlet 來設定多個音訊訊息或傳輸目的地。

設定未指派號碼表的方式取決於其使用方式。 如果您的特定號碼已不再使用，而您想要播放專為每個數位提供的訊息，您可以在 [未指定的數位] 資料表中輸入那些特定的數位。 例如，如果您變更了客戶服務服務台的號碼，您可以輸入舊的客戶服務號碼，並將其與提供新號碼的公告建立關聯。 如果您想要在呼叫未獲指派之號碼的任何人（例如，針對離開貴組織的員工）發出一般訊息，您可以為組織中的所有有效延伸輸入範圍。 每當來電者撥打目前未指派的號碼時，就會呼叫 [未指定的數位] 資料表。

在 Lync Server 2013 中，宣告應用程式會自動與回應群組應用程式一起安裝。 宣告與回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，這兩個應用程式都會自動部署。

</div>

<span> </span>

</div>

</div>

</div>

