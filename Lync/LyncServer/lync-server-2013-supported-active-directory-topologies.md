---
title: Lync Server 2013：支援的 Active Directory 拓撲
description: Lync Server 2013：支援的 Active Directory 拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ce820a36cb033933b423e01deb5a3049ed3ea2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575309"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Lync Server 2013 中支援的 Active Directory 拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-02_

Lync Server 2013 支援與 Microsoft Lync Server 2010 和 Microsoft Office 通訊伺服器 2007 R2 相同的 Active Directory 網域服務拓撲。 支援下列拓撲：

  - 具單一網域的單一樹系

  - 具單一樹狀結構和多個網域的單一樹系

  - 具多重樹狀結構和斷續命名空間的單一樹系

  - 中央樹系拓撲中的多重樹系

  - 資源樹系拓撲中的多重樹系

  - 具有 Exchange Online 之 Lync 資源樹系拓撲中的多個樹系

下圖識別本節圖例中使用的圖示。

**拓撲圖例**

![拓撲圖例](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "拓撲圖例")

<div>

## <a name="single-forest-single-domain"></a>單一樹系、單一網域

Lync Server、單一網域樹系支援的最簡單 Active Directory 拓撲是一般拓撲。

下圖說明單一網域 Active Directory 拓撲中的 Lync Server 部署。

**單一網域拓撲**

![單一網域拓撲](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "單一網域拓撲")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>單一樹系、多個網域

Lync Server 支援的另一個 Active Directory 拓撲是單一樹系，由一個根網域及一個或多個子域所組成。 在這種類型的 Active Directory 拓撲中，您建立使用者的網域可能與您部署 Lync Server 的網域不同。 但是，如果您部署前端集區，您就必須在單一網域內部署集區中的所有前端伺服器。 適用于 Windows 通用管理員群組的 Lync Server 支援可啟用跨網域管理。

下圖說明具有多個網域之單一樹系的部署。 在此圖中，使用者圖示會顯示使用者帳戶所在的網域，箭號會指向 Lync Server 集區所在的網域。 使用者帳戶包含下列項目：

  - 與 Lync Server 集區在相同網域中的使用者帳戶

  - Lync Server 集區的不同網域中的使用者帳戶

  - 具有 Lync Server 集區之網域之子域中的使用者帳戶

**具多重網域的單一樹系**

![具多重網域的單一樹系](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "具多重網域的單一樹系")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>單一樹系、多重樹狀結構

多重樹狀結構的樹系拓撲是由兩個以上的網域組成，這些網域定義獨立的樹狀結構和個別的 Active Directory 命名空間。

下圖說明具多重樹狀結構的單一樹系。 在此圖中，使用者圖示會顯示使用者帳戶所在的網域、實線指向位於相同或不同網域中的 Lync 伺服器集區，而虛線指向位於其他樹狀目錄中的 Lync Server 集區。 使用者帳戶包含下列項目：

  - 與 Lync Server 集區在相同網域中的使用者帳戶

  - 不同網域中的使用者帳戶 (，但與 Lync Server 集區) 相同的樹狀目錄

  - Lync Server 集區的不同樹狀目錄中的使用者帳戶

**具多重樹狀結構的單一樹系**

![具多重樹狀結構的單一樹系](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "具多重樹狀結構的單一樹系")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>多重樹系、中央樹系

Lync Server 支援在中央樹系拓撲中設定多個樹系。 中央樹系拓撲使用中央樹系中的連絡人物件來代表其他樹系的使用者。 中央樹系也會為此樹系中的任一使用者裝載其使用者帳戶。 目錄同步處理產品 (例如 Microsoft Identity Integration Server (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1)) 會管理組織中的使用者帳戶生命週期：在其中一個樹系中建立新的使用者帳戶，或在樹系中刪除使用者帳戶時，目錄同步處理產品就會在中央樹系中同步處理對應的連絡人。

中央樹系有下列優點：

  - 在單一樹系中集中執行 Lync Server 的伺服器。

  - 使用者可以搜尋任何樹系中的其他使用者，並與之通訊。

  - 使用者可以檢視任何樹系中其他使用者的目前狀態。

  - 當建立或移除使用者帳戶時，目錄同步處理產品會自動新增及刪除中央樹系中的連絡人物件。

下圖說明中央樹系拓撲。 在此圖中，主控 Lync Server 的網域（位於中央樹系中）和每個僅使用者網域（位於不同樹系中）皆有雙向信任關係。 個別使用者樹系中的架構不需要擴充。

**中央樹系拓撲**

![中央樹系拓撲](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央樹系拓撲")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>多重樹系、資源樹系

在資源樹系拓撲中，有一個樹系專用於執行伺服器應用程式，例如 Microsoft Exchange Server 和 Lync Server。 資源樹系會裝載伺服器應用程式以及作用中使用者物件的同步表示，但不包含已啟用登入的使用者帳戶。 資源樹系是當做使用者物件所在的其他樹系的共用服務環境。 使用者樹系與資源樹系之間有樹系層級的信任關係。 當您在此類型的拓撲中部署 Lync Server 時，您會在資源樹系中為使用者樹系中的每個使用者帳戶建立一個已停用的使用者物件。 如果已在資源樹系中部署 Microsoft Exchange，則已停用的使用者帳戶可能已存在。 目錄同步處理產品 (例如 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1)) 會管理使用者帳戶的生命週期。 在其中一個使用者樹系中建立新的使用者帳戶，或在樹系中刪除使用者帳戶時，目錄同步處理產品就會在資源樹系中同步處理對應的使用者表示。

此拓撲可以為管理多重樹系的組織提供共用的服務基礎結構，或用來將 Active Directory 物件的管理作業與其他管理作業區隔開來。公司基於安全考量，要將 Active Directory 管理作業隔離起來時，通常會選擇此拓撲。

此拓撲的優點是，您只需在單一樹系 (也就是資源樹系) 中擴充 Active Directory 架構。

下圖說明資源樹系拓撲。

**資源樹系拓撲**

![Active Directory 資源樹系拓撲](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 資源樹系拓撲")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>具有 Exchange Online 之 Lync 資源樹系拓撲中的多個樹系

在此拓撲中，一或多個樹系位於內部部署，而且專用於主控 Active Directory 使用者帳戶。 資源樹系位於內部部署，由協力廠商主機服務提供者維護。 資源樹系僅包含從內部部署使用者帳戶樹系 (s) 中的 Lync Server 部署和使用者帳戶的同步複寫。 不包含啟用登入的使用者帳戶。 Exchange 是在內部部署使用者帳戶樹系中部署 (s) 與 Exchange Online (混合式) ，或內部部署使用者帳戶的電子郵件服務，由 Exchange Online 獨佔提供。

資源樹系充當內部部署 Active Directory 樹系的共用服務環境 (s) 使用者物件所在的位置。 使用者帳戶樹系 (s) 具有與資源樹系的單向樹系層級信任關係。 當您在此類型的拓撲中部署 Lync Server 時，您會在資源樹系中為使用者樹系中的每個使用者帳戶建立一個已停用的使用者物件。 目錄同步處理產品 (例如 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1)) 會管理使用者帳戶的生命週期。 在其中一個使用者樹系中建立新的使用者帳戶，或在樹系中刪除使用者帳戶時，目錄同步處理產品就會在資源樹系中同步處理對應的使用者表示。 如需設定多樹系部署的詳細資訊，請參閱 [在多樹系架構中部署 Lync， (第三個樹系的 lync 具有 Exchange 混合) ](https://go.microsoft.com/fwlink/p/?linkid=513216)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

