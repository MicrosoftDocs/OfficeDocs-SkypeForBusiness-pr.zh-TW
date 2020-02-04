---
title: Lync Server 2013：支援的 Active Directory 拓撲
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
ms.openlocfilehash: 3e4aca368f6ea7d5b31a1cfe74273dfbd42a6594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Lync Server 2013 中支援的 Active Directory 拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-02_

Lync Server 2013 支援與 Microsoft Lync Server 2010 和 Microsoft Office 通訊伺服器 2007 R2 相同的 Active Directory 網域服務拓撲。 支援下列拓撲：

  - 單一目錄林與單一網域

  - 具有單一樹狀結構和多個網域的單一目錄林

  - 具有多個樹和不連續命名空間的單一目錄林

  - 中央目錄林拓撲中的多個林

  - 資原始目錄林拓朴中的多個目錄林

  - 使用 Exchange Online 的 Lync 資原始目錄林拓撲結構中有多個目錄林

下圖說明本節中的圖例所使用的圖示。

**拓撲圖例索引**

![拓撲圖例索引](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "拓撲圖例索引")

<div>

## <a name="single-forest-single-domain"></a>單一目錄林、單一網域

Lync Server （單一網域林）支援的最簡單的 Active Directory 拓撲是常見的拓撲。

下圖說明單一網域 Active Directory 拓撲中的 Lync Server 部署。

**單一網域拓撲**

![單一網域拓撲](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "單一網域拓撲")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>單一目錄林、多個網域

Lync Server 支援的另一個 Active Directory 拓撲是一個由根網域以及一個或多個子網域組成的單一目錄林。 在這種類型的 Active Directory 拓撲中，您建立使用者的網域可能與您部署 Lync Server 的網域不同。 不過，如果您要部署前端池，您必須在單一網域中部署該池中的所有前端伺服器。 Windows 通用管理員群組的 Lync Server 支援可啟用跨網域管理。

下圖說明單一樹林中有多個網域的部署。 在此圖中，使用者圖示會顯示使用者帳戶所在的網域，而箭頭則指向 Lync 伺服器池所在的網域。 使用者帳戶包括下列專案：

  - 與 Lync Server pool 在同一個網域中的使用者帳戶

  - Lync Server pool 的不同網域中的使用者帳戶

  - 網域子域中擁有 Lync 伺服器池的使用者帳戶

**具多重網域的單一樹系**

![具多重網域的單一樹系](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "具多重網域的單一樹系")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>單一目錄林、多個樹

多重樹狀目錄林拓朴由兩個以上的網域組成，這些網域定義獨立的樹狀結構和獨立的 Active Directory 命名空間。

下圖說明單一擁有多個樹的目錄林。 在此圖中，使用者圖示會顯示使用者帳戶所在的網域、實線指向位於相同或不同網域的 Lync 伺服器池，而虛線則指向位於不同樹狀結構的 Lync Server pool。 使用者帳戶包括下列專案：

  - 與 Lync Server pool 在同一個網域中的使用者帳戶

  - 不同網域中的使用者帳戶（但與 Lync 伺服器池的同一個樹狀結構一樣）

  - Lync Server 文件庫不同樹狀結構中的使用者帳戶

**具多重樹狀結構的單一樹系**

![具多重樹狀結構的單一樹系](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "具多重樹狀結構的單一樹系")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>多個目錄林，中央目錄林

Lync Server 支援多個在中央目錄林拓撲結構中設定的目錄林。 中央林拓撲在中央林中使用連絡人物件來代表其他林中的使用者。 中央目錄林也會為此林中的任何使用者託管使用者帳戶。 目錄同步處理產品，例如 Microsoft 身分識別整合伺服器（MIIS）、Microsoft Forefront 身分識別管理員（FIM）2010或 Microsoft 身分識別週期管理員（ILM）2007功能套件1（FP1），管理使用者帳戶在其中的生命週期組織：當您在其中一個目錄林中建立新的使用者帳戶，或從樹林中刪除使用者帳戶時，目錄同步處理產品會同步處理中央林中的對應連絡人。

中央林具有下列優點：

  - 在單一目錄林中執行 Lync Server 的伺服器是集中式。

  - 使用者可以在任何林中搜尋並與其他使用者通訊。

  - 使用者可以在任何林中查看其他使用者的目前狀態。

  - 目錄同步處理產品會在建立或移除使用者帳戶時，自動在中央林中新增和刪除連絡人物件。

下圖說明中央林拓撲。 在此圖中，託管 Lync Server 的網域（位於中央林中）與每個使用者專用的網域（分別位於不同的林中）都有雙向信任關係。 個別使用者林內的架構不需要進行延伸。

**中央樹系拓撲**

![中央樹系拓撲](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央樹系拓撲")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>多個林、資原始目錄林

在資原始目錄林拓朴中，有一個目錄林專用於執行伺服器應用程式，例如 Microsoft Exchange Server 和 Lync Server。 資原始目錄林主持伺服器應用程式及作用中使用者物件的同步表示，但不包含登入的使用者帳戶。 資原始目錄林充當使用者物件所在之其他目錄林的共用服務環境。 使用者目錄林與資原始目錄林有林層級的信任關係。 當您在這種類型的拓朴中部署 Lync Server 時，您會在資原始目錄林中為使用者樹林中的每個使用者帳戶建立一個停用的使用者物件。 如果 Microsoft Exchange 已部署在資原始目錄林中，停用的使用者帳戶可能已經存在。 目錄同步處理產品，例如 MIIS、Microsoft Forefront 身分識別管理員（FIM）2010或 Microsoft 身分識別週期管理員（ILM）2007功能套件1（FP1），管理使用者帳戶的生命週期。 當您在其中一個使用者林中建立新的使用者帳戶，或是從樹林中刪除使用者帳戶時，目錄同步處理產品會同步處理資原始目錄林中對應的使用者表示。

這個拓撲可用來為組織中管理多個目錄林的服務提供共用基礎結構，或是將 Active Directory 物件的管理與其他管理區分開。 需要隔離 Active Directory 系統管理以安全原因的公司，通常會選擇此拓撲。

這個拓撲提供限制將 Active Directory 架構延伸到單一目錄林（也就是資原始目錄林）的好處。

下列圖表說明資源林拓撲。

**資源林拓撲**

![Active Directory 資源樹系拓撲](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 資源樹系拓撲")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>使用 Exchange Online 的 Lync 資原始目錄林拓撲結構中有多個目錄林

在此拓撲中，一個或多個目錄林位於內部部署，且專用於託管 Active Directory 使用者帳戶。 資原始目錄林位於內部部署，且由協力廠商主機服務提供者維護。 資原始目錄林只包含 Lync Server 部署與內部部署使用者帳戶林中的使用者帳戶同步複製。 它不包含登入的使用者帳戶。 Exchange 是在結合 Exchange Online （混合式）的內部部署使用者帳戶目錄林中，或以 exchange Online 為內部部署使用者帳戶提供電子郵件服務。

資原始目錄林充當使用者物件所在之內部部署 Active Directory 林的共用服務環境。 使用者帳戶目錄林與資原始目錄林有單一的方式林層級信任關係。 當您在這種類型的拓朴中部署 Lync Server 時，您會在資原始目錄林中為使用者樹林中的每個使用者帳戶建立一個停用的使用者物件。 目錄同步處理產品，例如 MIIS、Microsoft Forefront 身分識別管理員（FIM）2010或 Microsoft 身分識別週期管理員（ILM）2007功能套件1（FP1），管理使用者帳戶的生命週期。 當您在其中一個使用者林中建立新的使用者帳戶，或是從樹林中刪除使用者帳戶時，目錄同步處理產品會同步處理資原始目錄林中對應的使用者表示。 如需有關設定多目錄林部署的詳細資訊，請參閱[在多林結構（含 Exchange 混合式的合作夥伴託管的 lync）中部署 lync](http://go.microsoft.com/fwlink/p/?linkid=513216)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

