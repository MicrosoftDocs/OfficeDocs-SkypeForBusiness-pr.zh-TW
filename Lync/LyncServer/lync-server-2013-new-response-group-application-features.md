---
title: Lync Server 2013：新回應群組應用程式功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013 中的新回應群組應用程式功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

透過回應群組應用程式，您可以將來電傳送給指定的人員，以進行特殊用途（例如客戶服務、內部技術支援人員或部門的一般電話支援）。

下列回應群組應用程式功能是 Lync Server 2013 中的新功能：

  - **管理員角色**
    
    Lync Server 2013 引入了新的 [回應群組管理員] 角色。 現在，回應群組有兩個管理角色： [回應群組管理員] 和 [回應群組管理員]。 雖然回應群組管理員仍可為任何回應群組設定任何元素，但管理員只能針對其擁有的回應群組設定特定元素。
    
    管理模型的這項改進帶來了回應群組的伸縮性，特別是大型部署案例。

  - **高可用性**
    
    回應群組應用程式的高可用性支援（以 SQL Server 鏡像的形式），是在 Lync Server 2013 的整體設定和部署的整體配置和部署中啟用。 如果您設定高可用性，且失去主要後端伺服器的連線，回應群組功能不會受到利用鏡像後端伺服器的影響。
    
    在整個 Lync Server 2013 高可用性設定之外，無法個別啟用或設定回應群組應用程式的 SQL Server 鏡像支援。

  - **災害復原**
    
    已啟用回應群組應用程式的災害復原支援，這是整個 Lync Server 2013 災害復原設定中的設定與部署的一部分。 此外，回應群組的匯入及匯出 Cmdlet 支援將容錯移轉程式加入到主要池或新的池中。 如果主要池中出現停機，回應群組可以容錯移轉至備份池，然後在中斷結束時回到主要池或新的池中。

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃回應群組](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

