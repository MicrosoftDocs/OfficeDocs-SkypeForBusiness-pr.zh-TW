---
title: Lync Server 2013：定義封存需求
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
ms.openlocfilehash: 4a5f789f390e1cf104a0dc1b3a10a4116ba38c03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521660"
---
# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中定義封存需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

如果您的組織必須遵循相容性法規，您可以部署封存，以啟用 Lync Server 2013 立即訊息 (IM) 和會議 (會議) 的封存支援。 如需可封存之內容類型的詳細資訊，請參閱規劃檔中的封存 [簡介 In Lync Server 2013](lync-server-2013-overview-of-archiving.md) 。

若要執行封存，您必須先決定如何符合組織的封存需求。 這需要判斷下列專案：

  - **何時部署**封存。 您可以將封存部署為初始 Lync Server 2013 部署的一部分，也可以將其新增至現有的部署。 您可以使用拓撲產生器來部署封存，將其新增至您的拓撲，然後發行拓撲。

  - **是否封存內部或外部通訊**。 您可以對內部使用者之間的通訊 (通訊啟用內部通訊的封存) 、外部通訊 (在內部網路以外至少包含一位使用者的通訊) ，或是兩者。 您可以為整個組織指定這些選項，也可以為特定網站和集區指定這些選項。 根據預設，這兩個選項都不會啟用。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用 Microsoft Exchange 整合來儲存封存的資料，您的 Exchange 設定會控制是否要封存 Lync 通訊。 如果您的部署包含多個樹系，您必須同步處理 Lync Server 與 Exchange 之間的設定。 控制內部或外部通訊的封存只適用于 Lync 原則。 針對 Exchange 整合型封存，這兩項都將會封存或未封存。

    
    </div>

  - **為何啟用**封存。 您可以為全域層級的整個部署啟用和停用封存，也可以啟用和停用特定網站和使用者的封存。 在每個層級中，您會指定是否要啟用 IM 會話的封存 (對等) 、會議 (會議，也就是) 的多方會話，也是兩者。 預設會停用封存。

  - **組織中使用者的重要**封存。 如果您的組織中的封存非常重要，您可以指定 Lync Server 2013 在重要模式中執行，這會在封存失敗時封鎖 IM 和會議會話。 例如：
    
      - 如果封存服務暫時無法將訊息傳送給資料庫佇列或將訊息插入資料庫，則在恢復封存支援之前，部署項目會同時封鎖 IM 與會議功能。
    
      - 當會議使用者上載檔案，但該檔案卻無法複製到封存檔案存放區時，部署項目會在問題解決之前封鎖會議功能，但不會封鎖 IM 功能。
    
    您可以在全域層級、網站層級及集區層級設定此選項。 根據預設，不會啟用重要模式。

  - **是否使用 Microsoft Exchange 整合**。 此選項會將封存儲存與 Exchange 2013 儲存整合，讓您的 Lync Server 封存資料和 Exchange 2013 封存資料會一起儲存在 Exchange 中。 您可以使用 Microsoft Exchange 整合，儲存位於 Exchange 2013 （如果使用者的信箱已放在 In-Place 暫止）的封存資料。 如果您沒有 Exchange 2013 部署，或者您不想要將其與其整合，或者如果您有任何 Lync 使用者未裝載于 Exchange 2013，您可以使用 SQL Server 將封存的資料儲存在 Lync 通訊中，以部署個別的封存資料庫。 您可以在全域層級、網站層級及集區層級設定 Microsoft Exchange 整合選項。 依預設，不會啟用 Microsoft Exchange 整合功能。

  - 封存**資料的管理方式**。 封存資料庫不適用於長期保留，而 Lync Server 2013 不會提供電子探索 (搜尋) 的封存資料的解決方案，因此必須將資料移至其他儲存區。 Lync Server 提供一種會話匯出工具，可供您用來匯出封存的資料，並可建立已封存資料的可搜尋記錄。 針對全域原則，以及您建立的每個網站和使用者原則，您可以啟用資料清除，並指定下列其中一個選項：
    
      - 在經過指定的天數之後，同時清除匯出的封存資料與儲存的封存資料。 您可以指定的天數下限為 1 天。 您可以指定的天數上限為 2562 天。
    
      - 只清除匯出的封存資料。此選項會清除所有已經匯出，以及被工作階段匯出工具標示為可安心刪除的記錄。
    
    您可以在全域層級、網站層級及集區層級設定此選項。 預設不會啟用清除功能。

您可以使用下列方法來控制封存：

  - 封存**原則**。 您可以使用一或多個封存原則來啟用和停用內部及外部通訊的封存。 根據預設，不會啟用任何封存。 您可以使用預設全域原則，在部署中啟用或停用內部通訊、外部通訊或兩者的封存。 您無法刪除全域原則。 您可以指定一或多個選用的網站原則，針對特定網站啟用或停用內部及外部通訊的封存。 您也可以指定一或多個使用者原則，以啟用或停用特定使用者和使用者群組的封存。 使用者層級原則會覆寫網站原則。 網站層級原則會覆寫全域層級原則。 只有設定為使用原則的特定使用者才能執行使用者層級原則。 只有在至少有一位參與者的原則設定為啟用封存時，才會封存「立即訊息和會議」。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫位於 Exchange 2013 伺服器上之所有使用者的 Lync Server 封存原則。

    
    </div>

  - 封存**設定。** 您可以使用一或多個封存設定來指定本主題先前所述的大部分封存選項，但不允許使用封存原則來設定內部和外部通訊 (，如先前專案符號) 所述。 封存設定包括預設全域設定和選用的網站及集區設定。 您無法刪除全域設定。 集區層級設定會覆寫網站層級設定。 網站層級設定會覆寫全域層級設定。

在您的需求分析過程中，您必須決定如何設定全域封存設定和全域封存原則。 您也需要判斷任何網站層級封存設定、集區層級的封存設定、網站層級的封存原則，以及使用者層級的封存原則的需求。

如果您部署一個前端集區或 Standard Edition server 的封存，則應該針對部署中的所有其他前端集區和 Standard Edition server 啟用該封存。 您必須這麼做，因為需要封存其通訊的使用者可以應邀參加位於不同集區的群組 IM 交談或會議。 如果在主控交談或會議的集區上未啟用封存，所有會議資料可能都不會封存。 封存仍可用於啟用使用者和所有 IM 訊息的封存，但會議內容和事件可能不會封存。

<div>


> [!NOTE]  
> 若要在維護組織的安全性標準時，啟用管理工作委派，Lync Server 2013 &nbsp; 使用角色型存取控制 (RBAC) 。 透過 RBAC，系統管理許可權是透過指派使用者至預先定義的系統管理角色授與。 若要設定 Lync 封存原則和封存設定，必須將使用者指派給 CsArchivingAdministrator role (，除非在部署封存的伺服器上直接執行設定，而不是從其他電腦) 進行遠端處理。 如需 RBAC 的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。 如需封存部署所需之使用者權利、許可權及角色的清單，請參閱 <A href="lync-server-2013-deployment-checklist-for-archiving.md">部署檢查清單中</A>的封存（適用于規劃檔和部署檔中）的 Lync Server 2013。<BR>如果您使用 Microsoft Exchange 整合，設定 Exchange 原則需要適當的系統管理員許可權。 如需詳細資訊，請參閱 Exchange 2013 檔。



</div>

</div>

<span> </span>

</div>

</div>

</div>

