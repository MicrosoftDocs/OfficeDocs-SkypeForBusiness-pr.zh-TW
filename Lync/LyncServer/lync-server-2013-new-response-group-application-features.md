---
title: Lync Server 2013：新的回應群組應用程式功能
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
ms.openlocfilehash: f4ae3ad427164d8a948130e69fd54d1e6f8c37b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536850"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013 中新的回應群組應用程式功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

「回應群組」應用程式可讓您基於特殊目的將來電轉接和保留給指定人員，例如客戶服務、內部服務台或部門的一般電話支援。

下列回應群組應用程式功能是 Lync Server 2013 中的新功能：

  - **管理員角色**
    
    Lync Server 2013 引進新的回應群組管理員角色。 現在有兩個管理角色的回應群組：回應群組管理員和回應群組管理員。 當回應群組管理員仍可為任何回應群組設定任何元素時，管理員只可以設定特定元素，只適用于其擁有的回應群組。
    
    系統管理模型中的這項改進功能有利於回應群組的延展性，特別適用於大型部署案例。

  - **高可用性**
    
    以 SQL Server 鏡像的方式，回應群組應用程式的高可用性支援，是在 Lync Server 2013 的整體設定與部署的整體設定和部署中啟用的一部分。 如果您設定高可性且遺失與主要後端伺服器的連線，回應群組功能便不會因為使用鏡像的後端伺服器而受到影響。
    
    無法在整體 Lync Server 2013 高可用性設定外，個別啟用或設定回應群組應用程式的 SQL Server 鏡像支援。

  - **災害復原**
    
    在設定及部署成對的前端集區時（屬於整體 Lync Server 2013 災害復原設定的一部分），會啟用回應群組應用程式的嚴重損壞修復支援。 此外，回應群組匯入與匯出 Cmdlet 支援對備份集區的容錯移轉程序和對主要集區或新集區的容錯回復程序。 如果主要集區中發生中斷，回應群組即會容錯移轉至備份集區，然後在中斷回復之後容錯回復至主要集區或新集區。

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃回應群組](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

