---
title: Lync Server 2013： 新的回應群組應用程式的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37263eeb099ea468713526c20a2c6b14bed0694d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013 中的新回應群組應用程式功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

「回應群組」應用程式可讓您基於特殊目的將來電轉接和保留給指定人員，例如客戶服務、內部服務台或部門的一般電話支援。

下列回應群組應用程式的功能是 Lync Server 2013 的新增功能：

  - **管理員角色**
    
    Lync Server 2013 引進新的回應群組管理員角色。 現在有兩種管理角色的回應群組： 回應群組管理員及回應群組管理員。 雖然回應群組管理員仍然可以設定任何回應群組的任何項目，管理員可以設定僅限特定項目，僅適用於其所擁有的回應群組。
    
    系統管理模型中的這項改進功能有利於回應群組的延展性，特別適用於大型部署案例。

  - **高可用性**
    
    整體設定與 Lync Server 2013 的高可用性的部署的一部分，會啟用回應群組應用程式，在 SQL Server 鏡像，表單中的高可用性支援。 如果您設定高可性且遺失與主要後端伺服器的連線，回應群組功能便不會因為使用鏡像的後端伺服器而受到影響。
    
    支援 SQL Server 鏡像的回應群組應用程式不能個別啟用或設定的整體的 Lync Server 2013 的高可用性設定以外。

  - **災害復原**
    
    災害復原支援回應群組應用程式已啟用的設定資料庫和部署配對前端集區，屬於整體的 Lync Server 2013 災害復原設定的一部分。 此外，回應群組匯入與匯出 Cmdlet 支援對備份集區的容錯移轉程序和對主要集區或新集區的容錯回復程序。 如果主要集區中發生中斷，回應群組即會容錯移轉至備份集區，然後在中斷回復之後容錯回復至主要集區或新集區。

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中的回應群組](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

