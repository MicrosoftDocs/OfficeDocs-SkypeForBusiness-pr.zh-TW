---
title: Lync Server 2013： 定義封存需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110423897de0d4d8e280a44cd51c645ab479241a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中定義封存需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

如果您的組織必須遵循法規合規性，您可以部署封存，若要啟用封存支援適用於 Lync Server 2013 立即訊息 (IM) 和會議 （會議）。 如需可以封存的內容類型的詳細資訊，請參閱[概觀的封存 Lync Server 2013 中](lync-server-2013-overview-of-archiving.md)規劃文件。

若要實作封存，您需要先決定要如何符合您的組織需求的封存。 這需要決定下列：

  - **部署封存的時機**。 您可以將封存部署為初始 Lync Server 2013 部署的一部分，或您可以將它新增至現有的部署。 您將部署封存使用拓撲產生器將它新增至您的拓撲，然後再發行拓撲。

  - **是否要封存內部或外部通訊**。 您可以啟用外部通訊 （包含您的內部網路外的至少一位使用者的通訊），或兩者的封存內部通訊 （內部部署使用者之間的通訊）。 您可以指定這些選項的整個組織，或您可以將它們指定特定的網站與集區。 根據預設，會啟用這兩個選項。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用 Microsoft Exchange 整合來儲存封存的資料，您的 Exchange 設定會控制是否要封存的 Lync 通訊。 如果您的部署包含多個樹系，您必須同步處理 Lync Server 和 Exchange 之間的設定。 控制的內部或外部通訊封存 」 僅適用於 Lync 原則。 Exchange 整合封存，兩者都將封存或不會封存。

    
    </div>

  - **為什麼要啟用封存**。 您可以啟用及停用整個部署在全域層級的封存，您可以啟用及停用特定的網站和使用者的封存。 您指定是否要啟用封存 IM 工作階段 （對等端對端），在每個這些層級，會議 （會議，也就是多方工作階段），或兩者。 根據預設，會停用封存。

  - **如何重要封存為您組織中的使用者**。 如果封存是重要的組織中，您可以指定在封存失敗時封鎖 IM 與會議工作階段的關鍵模式下執行 Lync Server 2013。 例如：
    
      - 如果封存服務暫時無法將訊息傳送給資料庫佇列或將訊息插入資料庫，則在恢復封存支援之前，部署項目會同時封鎖 IM 與會議功能。
    
      - 當會議使用者上載檔案，但該檔案卻無法複製到封存檔案存放區時，部署項目會在問題解決之前封鎖會議功能，但不會封鎖 IM 功能。
    
    您可以在全域層級、 網站層級和集區層級設定此選項。 根據預設，不會啟用關鍵模式。

  - **是否要使用 Microsoft Exchange 整合**。 此選項，讓您的 Lync Server 封存資料和 Exchange 2013 封存的資料都會一起儲存在 Exchange 與您的 Exchange 2013 儲存體，封存存放區整合。 您可以使用 Microsoft Exchange 整合來儲存封存資料的使用者位於 Exchange 2013 中，如果他們的信箱已處於就地保留。 如果您沒有 Exchange 2013 部署中，如果您不想整合，或如果您有任何 Lync 使用者不位於 Exchange 2013，您可以使用 SQL Server 來儲存封存的資料從 Lync 通訊部署個別封存資料庫。 您可以在全域層級、 網站層級和集區層級設定 Microsoft Exchange 整合選項。 根據預設，不會啟用 Microsoft Exchange 整合。

  - **如何封存資料是以進行管理**。 封存資料庫不是長期保留和 Lync Server 2013 不提供 e-探索 （搜尋） 解決方案封存的資料，因此資料移至其他儲存區。 Lync Server 並提供您可以使用匯出封存的資料，以及而產生的封存資料的可搜尋記錄的工作階段匯出工具。 全域原則，以及您建立每個網站與使用者原則，您可以啟用資料清除，並指定下列選項之一：
    
      - 在經過指定的天數之後，同時清除匯出的封存資料與儲存的封存資料。 您可以指定的天數下限為 1 天。 您可以指定的天數上限為 2562 天。
    
      - 只清除匯出的封存資料。此選項會清除所有已經匯出，以及被工作階段匯出工具標示為可安心刪除的記錄。
    
    您可以在全域層級、 網站層級和集區層級設定此選項。 預設不會啟用清除功能。

您可以使用下列方法，以控制封存：

  - **封存原則**。 您可以使用一或多個封存原則來啟用及停用內部和外部通訊封存。 根據預設，會啟用任何封存。 您可以啟用或停用封存內部通訊、 外部通訊或兩者部署中使用預設的全域原則。 您無法刪除全域原則。 您可以指定一或多個選用的網站原則，以啟用或停用的特定網站的內部和外部通訊的封存。 您也可以指定一或多個使用者原則，以啟用或停用封存為特定使用者和使用者群組。 使用者層級原則會覆寫網站原則。 網站層級的原則會覆寫全域層級原則。 僅針對特定使用者設定為使用原則實作使用者層級原則。 群組立即訊息與會議已封存只有在至少一個參與者原則設定啟用封存。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫所有使用者都位於 Exchange 2013 伺服器上的 Lync Server 封存原則。

    
    </div>

  - **封存組態**。 使用下列一個或多個封存組態，以指定大部分的封存選項，將前文所述在本主題中，除了啟用內部與外部通訊封存 (如所述使用封存原則的設定上一個項目符號）。 封存組態包含選用的網站與集區設定與預設的全域設定。 您無法刪除全域設定。 集區層級設定會覆寫網站層級設定。 網站層級設定會覆寫全域層級設定。

需求分析的一部份，您必須決定如何設定全域封存設定資料庫和全域封存原則。 您也需要判斷您的任何網站層級的封存組態、 集區層級的封存組態、 網站層級的封存原則和使用者層級的封存原則的需求。

如果您的一個前端集區或 Standard Edition server 部署封存，您應該然後加以啟用的所有其他前端集區和 Standard Edition server 部署中。 您需要這麼做，因為其通訊所要封存的使用者可以邀請加入群組 IM 交談或會議裝載於另一個集區上。 如果主控交談或會議的集區上未啟用封存，可能不會封存所有會議資料。 封存來封存已啟用的使用者和所有 IM 訊息，仍然可以使用，但會議內容和事件可能不會封存。

<div>


> [!NOTE]  
> 若要啟用同時維持貴組織的安全性標準，Lync Server 2013 系統管理工作的委派&nbsp;使用角色型存取控制 (RBAC)。 使用 RBAC，管理特殊權限會授與預先定義的系統管理角色指派的使用者。 若要設定 Lync 封存原則和封存組態，使用者必須指派給 CsArchivingAdministrator 角色 (除非組態是直接在其中要部署封存，而不是從遠端伺服器上從另一部電腦)。 如需有關 RBAC 的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</A>。 使用者權限、 權限，和封存部署所需的角色清單，請參閱<A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的封存的部署檢查清單</A>，這是在規劃文件和部署文件中使用。<BR>如果您使用 Microsoft Exchange 整合，設定 Exchange 原則，會需要適當的系統管理員權限和權限。 如需詳細資訊，請參閱 < Exchange 2013 文件。



</div>

</div>

<span> </span>

</div>

</div>

</div>

