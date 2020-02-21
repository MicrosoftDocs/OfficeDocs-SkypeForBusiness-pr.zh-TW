---
title: 宣告應用程式的 Lync Server 2013： 概觀
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
ms.openlocfilehash: 2ffccccdc92df2d64424a0cc240dbda51f636a3d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的宣告應用程式概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-13_

當您部署宣告應用程式時，您需要設定會決定當有人撥打未指派的號碼時應採取的動作未指派號碼表。 未指派號碼表格包含的有效值為組織的電話號碼範圍，並指定哪些宣告應用程式會處理每個範圍。 當來電者撥打組織有效，但不指派給任何人的電話號碼時，Lync Server 會查閱未指派號碼的路由表格中的數字、 識別哪一個範圍中，就是數字落和宣告將通話路由傳送指定為該範圍的應用程式。 宣告應用程式接聽來電播放的語音訊息 （如果您設定要這麼做），然後中斷來電或將其移至預定目的地，例如運算子。 您可以使用 Lync Server 管理命令介面指令程式，來設定多個音訊的郵件，或傳輸的目的地。

設定未指派號碼表的方式取決於其使用方式。如果您有不再使用的特定號碼，而且想要播放專為各個號碼而設計的訊息，則可以在未指派號碼表中輸入那些特定號碼。例如，如果您變更了客戶服務中心的號碼，則可以輸入舊的客戶服務號碼，並將其與宣告相關聯，以提供新號碼。如果您想要對撥打未指派之號碼的任何人 (如離職員工) 播放一般訊息，則可以輸入您組織中所有有效分機的範圍。只要來電者撥打目前未指派的號碼，就會叫用未指派號碼表。

在 Lync Server 2013 中，宣告應用程式會自動安裝與回應群組應用程式。 宣告和回應群組應用程式是標準的企業語音部署的元件： 當您部署企業語音時，這些應用程式均會自動部署。

</div>

<span> </span>

</div>

</div>

</div>

