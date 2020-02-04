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
ms.openlocfilehash: a3cee7269620a9525456e40604ae3f1d1c2cf33d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中定義封存需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

如果您的組織必須遵循合規性規範，您可以部署封存，以啟用 Lync Server 2013 立即訊息（IM）和會議（會議）的封存支援。 如需有關可封存之內容類型的詳細資訊，請參閱規劃檔中的[Lync Server 2013 存檔](lync-server-2013-overview-of-archiving.md)。

若要實施封存，您必須先決定如何符合貴組織的存檔需求。 這需要判斷下列事項：

  - **部署存檔**的時機。 您可以將封存部署為您最初的 Lync Server 2013 部署的一部分，或者您可以將它新增到現有的部署。 您可以使用拓撲建立器將封存新增到您的拓撲結構，然後發佈拓撲。

  - **是否封存內部或外部通訊**。 您可以針對內部通訊（內部使用者之間的通訊）、外部通訊（至少包含一個使用者在內部網路以外的通訊），或兩者皆啟用封存。 您可以為整個組織指定這些選項，也可以針對特定的網站和池加以指定。 預設不會啟用任何選項。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用 Microsoft Exchange 整合來儲存封存的資料，Exchange 設定就會控制 Lync 通訊是否已封存。 如果您的部署包含多個目錄林，您必須同步處理 Lync Server 與 Exchange 之間的設定。 [控制內部或外部通訊的封存] 只適用于 Lync 原則。 針對 Exchange 整合式封存，這兩者都會封存或未封存。

    
    </div>

  - **為什麼要啟用**封存。 您可以在全域層級為整個部署啟用和停用封存，而且您可以針對特定的網站和使用者啟用和停用封存。 在每個階層，您可以指定是否要啟用 IM 會話（對等）、會議（會議，也就是多方會議），或是兩者。 根據預設，封存是停用的。

  - **貴組織中的使用者的重要存檔方式**。 如果存檔在您的組織中是至關重要的，您可以指定 Lync Server 2013 在 [重要] 模式中執行，這會在歸檔失敗時封鎖 IM 和會議會話。 例如：
    
      - 如果封存服務暫時無法傳送訊息到資料庫佇列或將訊息插入資料庫），則 IM 和會議功能會在部署期間封鎖，直到還原封存支援為止。
    
      - 如果會議使用者上傳檔案，但無法將檔案複製到 [封存檔案] 存放區，會議功能會在部署期間封鎖，直到問題解決為止，但不會封鎖 IM 功能。
    
    您可以在 [全域] 層級、[網站層級] 和 [池] 層級設定此選項。 根據預設，不會啟用 [關鍵模式]。

  - **是否要使用 Microsoft Exchange 整合**。 此選項會整合儲存與 Exchange 2013 儲存空間的儲存空間，讓您的 Lync Server 封存的資料和 Exchange 2013 存檔的資料會儲存在 Exchange 中。 您可以使用 Microsoft Exchange 整合來儲存駐留在 Exchange 2013 的使用者的存檔資料，如果其信箱已放在就地保留中。 如果您沒有 Exchange 2013 部署，或是您不想要將它整合到 exchange 2013，或者如果您有任何不是託管于 Exchange 的 Lync 使用者，您可以使用 SQL Server 從 Lync 通訊儲存已存檔的資料，以部署個別的存檔資料庫。 您可以在 [全域] 層級、[網站層級] 和 [池] 層級設定 Microsoft Exchange 整合選項。 根據預設，不會啟用 Microsoft Exchange 整合。

  - **存檔資料的管理方式**。 存檔資料庫不適用於長期保留，而且 Lync Server 2013 不會提供電子探索（搜尋）方案來儲存已封存的資料，因此需要將資料移到其他儲存空間。 Lync Server 提供可供您用來匯出封存資料的 [會話匯出] 工具，這會建立已歸檔資料的可搜尋記錄。 針對全域原則，以及您建立的每個網站和使用者原則，您可以啟用資料清除，並指定下列其中一個選項：
    
      - 在特定天數之後，清除匯出的存檔資料並儲存已儲存的資料。 您可以指定的天數最少為一天。 您最多可以指定2562天的天數。
    
      - 僅清除匯出的存檔資料。 這個選項會清除 [會話匯出] 工具已匯出並標示為可安全刪除的所有記錄。
    
    您可以在 [全域] 層級、[網站層級] 和 [池] 層級設定此選項。 根據預設，不會啟用 [清除]。

您可以使用下列方法來控制存檔：

  - **存檔原則**。 您可以使用一或多個存檔原則來啟用和停用內部與外部通訊的封存。 根據預設，不會啟用任何封存。 您可以透過使用預設的全域原則，在您的部署中啟用或停用內部通訊、外部通訊或兩者的封存。 您無法刪除全域原則。 您可以指定一或多個選用的網站原則來啟用或停用針對特定網站進行內部與外部通訊的封存。 您也可以指定一或多個使用者原則來啟用或停用特定使用者與使用者群組的存檔。 使用者層級原則會覆寫網站原則。 網站層級原則會覆寫全域層原則。 使用者層級原則只會針對設定為使用原則的特定使用者執行。 只有在至少一個參與者設定為啟用封存原則時，才會將 [立即訊息] 與 [會議] 群組封存。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫所有駐留在 Exchange 2013 伺服器上的使用者的 Lync Server 封存原則。

    
    </div>

  - **存檔**設定。 您可以使用一或多個存檔設定來指定本主題前面所述的大部分存檔選項，除了允許封存內部和外部通訊（使用 [封存原則] 進行設定）之外，如以下所述。上一個專案符號）。 封存配置包括預設的全域配置以及選用的網站和池設定。 您無法刪除全域配置。 池層級的設定會覆寫網站層級的配置。 網站層級配置會覆寫全域層級設定。

作為需求分析的一部分，您必須決定如何設定全域封存配置和全域歸檔原則。 您也需要針對任何網站層級歸檔設定、池層級的歸檔設定、網站層級的歸檔原則，以及使用者層級歸檔原則，來判斷您的需求。

如果您部署的是一個前端池或標準版伺服器的封存，則應該針對您部署中的所有其他前端池和標準版伺服器啟用該歸檔。 您必須執行此動作，因為需要封存其通訊的使用者可以受邀加入群組 IM 交談或託管于不同的池中的會議。 如果在託管或會議所在的池中未啟用 [封存]，所有的會議資料都可能無法封存。 封存功能仍適用于已啟用的使用者和所有 IM 訊息，但是會議內容和事件可能不會封存。

<div>


> [!NOTE]  
> 若要在維護貴組織的安全性標準時啟用管理工作委派，Lync Server&nbsp;2013 使用角色式存取控制（RBAC）。 使用 RBAC，系統會將使用者指派至預先定義的管理角色，以獲得系統管理許可權。 若要設定 Lync 歸檔原則和封存設定，使用者必須指派給 CsArchivingAdministrator 角色（除非是直接在部署歸檔的伺服器上執行，而不是從另一部電腦遠端完成）。 如需 RBAC 的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。 如需封存部署所需的使用者權利、許可權和角色清單，請參閱 Lync Server 2013 中的 [封存]<A href="lync-server-2013-deployment-checklist-for-archiving.md">部署核對清單</A>（在規劃檔和部署檔中都有提供）。<BR>如果您使用的是 Microsoft Exchange 整合，則 Exchange 原則的設定需要適當的系統管理員權力和許可權。 如需詳細資訊，請參閱 Exchange 2013 檔。



</div>

</div>

<span> </span>

</div>

</div>

</div>

