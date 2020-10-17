---
title: Lync Server 2013：封存的運作方式
description: Lync Server 2013：封存的運作方式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a5ef19c0781b4faa279a6aad46ac34b83ae0f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543379"
---
# <a name="how-archiving-works-in-lync-server-2013"></a>Lync Server 2013 中的封存運作方式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

Lync Server 2013 封存提供的選項可協助您符合您的合規性需求。 若要以最有效地符合組織需求的方式來實施及維護它，您應該瞭解：

  - 可以封存哪些資訊。

  - 如何在部署中啟用和停用封存。

  - 您可以設定來控制如何實作封存的封存選項。

<div>

## <a name="what-information-can-be-archived"></a>可以封存哪些資訊？

可以封存下列類型的內容：

  - 對等立即訊息

  - 會議，其為多方立即訊息

  - 會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)

  - 在會議期間共用白板與投票

不會封存下列類型的內容：

  - 對等檔案傳輸

  - 對等立即訊息和會議的音訊/視訊

  - 對等立即訊息和會議的桌面與應用程式共用

Lync Server 也不會封存持久聊天交談。 若要封存持久聊天對話，您必須啟用和設定規范服務，該服務是可與 Microsoft Lync Server 2013，Persistent Chat Server 一起部署的元件。 如需詳細資訊，請參閱規劃檔中的在 [Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md) 。

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>如何開始使用封存？

當您部署伺服器時，封存會自動安裝於每部前端伺服器上，但在您設定封存之前不會加以啟用。您設定封存的方式是根據您部署封存的方式來決定：

  - **使用 Microsoft Exchange 整合進行封存。** 如果您擁有位於 Exchange 2013 的使用者，且已將其信箱置於 In-Place 保留狀態，您可以選取此選項，以整合 Lync Server 2013 儲存體與 Exchange storage。 如果您選擇 [Microsoft Exchange 整合] 選項，您可以使用 Exchange 2013 原則和設定來控制這些使用者之 Lync Server 2013 資料的封存。

  - **使用 Lync Server 封存資料庫進行封存。** 如果您有未位於 Exchange 2013 的使用者，或其信箱未放在 In-Place 保留中的使用者，或是您不想要在部署中使用任何或所有使用者的 Microsoft Exchange 整合，您可以使用 SQL Server 部署 Lync Server 封存資料庫，以儲存使用者的封存資料。 在此情況下，Lync Server 2013 封存原則和設定會決定封存是否已啟用以及如何執行。 若要使用 Lync Server 2013，您必須將適當的 SQL Server 資料庫新增至您的拓撲，併發行拓撲。

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>使用 Microsoft Exchange 整合時的封存設定

如果您的使用者位於 Exchange 2013，而且其信箱已放在 In-Place 暫止狀態，您可以選擇 [ **Microsoft Exchange 整合** ] 選項 (本節稍後所述) 封存使用者的 Lync server 2013，然後指定 Exchange In-Place 保留原則和設定，以及 Lync server 設定來控制下列各項：

  - 是否要封存 IM、會議或兩者。

  - 是否要為您的 Lync Server 部署實施重要模式。

  - Microsoft Exchange 整合選項的選取範圍，使用 Exchange 2013 儲存封存的資料。

本節稍後會說明這些 Lync Server 2013 封存設定選項。 如需如何設定 Exchange In-Place 保留原則及設定以支援封存的詳細資訊，請參閱 Exchange 2013 產品檔。

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>使用 Lync Server 封存資料庫儲存時進行封存設定

若要使用 Lync Server 封存資料庫 (使用 SQL Server 資料庫) 若要封存部署中任何使用者的資料，您可以設定 Lync Server 封存原則，以控制是否為這些使用者啟用封存功能。 在每個封存原則中，您可以針對下列其中一項或兩項來啟用或停用封存：

  - 內部通訊

  - 外部通訊

根據預設，不會在任何 Lync Server 封存原則中啟用內部通訊或外部通訊的封存。 您可以使用 Lync Server 2013 控制台或在 Lync Server 2013 管理命令介面中使用 Cmdlet 來啟用及停用通訊。

Lync Server 2013 封存原則包括下列專案：

  - **全域封存原則**。 此為預設的封存原則，可以套用至您的整個部署。 它會在您部署 Lync Server 2013 時建立，而且預設會同時停用內部和外部通訊的封存。 您無法刪除此原則。 如果您選擇刪除選項，即會將全域原則重設為預設設定。

  - **網站封存原則**。您可以選擇性地為一或多個指定網站啟用或停用封存，作法是針對該網站建立和設定網站層級的封存原則。當您建立網站層級的封存原則時，預設不會啟用封存。您可以刪除任何您建立之網站層級的封存原則。網站層級的封存原則優先於全域原則，但僅適用於原則中指定的網站。例如，如果您在全域原則中針對內部與外部通訊啟用封存，然後建立一個網站原則以針對外部通訊停用封存，則只會針對該網站封存內部通訊。

  - **使用者封存原則**。您可以選擇性地為一或多個特定使用者或使用者群組啟用或停用封存，作法是為指定的使用者和使用者群組建立、設定及套用使用者層級的封存原則。當您建立使用者層級的封存原則時，預設不會啟用封存。您可以刪除任何您建立之使用者層級的封存原則，而且可以變更要套用封存原則的使用者與使用者群組。使用者層級的封存原則優先於全域原則及所有網站原則，但僅適用於套用原則的使用者和使用者群組。例如，如果您在全域原則中針對內部與外部通訊停用封存、建立一個網站層級的原則以針對內部與外部通訊啟用封存，然後建立一個使用者層級的原則以針對外部通訊停用封存，則系統將針對所有網站使用者的外部與內部通訊封存通訊，但您套用使用者層級原則的使用者例外，只會為他們封存內部通訊。

如需如何在部署封存時設定初始封存原則的詳細資訊，請參閱部署檔中的設定 [和指派 Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) 中的封存原則。 如需使用封存原則來啟用及停用部署後的通訊的詳細資訊，請參閱 Operations 檔中的 [管理 Lync Server 2013 中的內部及外部通訊](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 的封存。

<div>


> [!NOTE]  
> 如果您同時執行這兩種 Lync Server 2013 封存資料庫並啟用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫 Lync Server 封存原則，但僅限於位於 Exchange 2013 的使用者，且其信箱置於 In-Place 保留狀態。 Lync 封存取決於 Microsoft Exchange In-Place 暫止原則。



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>我可以使用哪些選項來設定封存？

除了使用原則及啟用與停用封存，您還有其他封存選項可用來為整個部署進行設定，而且可以選擇性地針對特定的網站與集區進行設定。 您可以使用一或多個封存設定來控制大部分封存選項，這些選項可在 Lync Server 2013 控制台中使用，但也有另一個僅可用於設定的選項，使用 Lync Server 2013 管理命令介面。

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Lync Server 2013 控制台中的封存設定選項

每個封存設定都會提供下列選項：

部署封存時會自動建立全域層級的設定，全域層級的設定可加以設定，但不能刪除。如果您選取選項來刪除全域設定，即會將設定重設為預設值。您可以建立多個網站與集區設定，與全域設定一起使用來控制封存設定。針對全域設定及每個台站與集區設定，您會有下列選項：

  - 停用封存、僅針對立即訊息 (IM) 啟用封存，或者針對 IM 和會議啟用封存

  - 設定重要模式，以在 Lync 伺服器失敗的事件中封鎖 IM 和會議會話。 失敗包含下列項目：
    
      - **IM**。 Lync Server storage service 發生問題。 在此情況下，會針對已啟用封存的使用者封鎖 IM。
    
      - **會議**。失敗可能是無法使用的檔案共用，或是儲存服務發生問題。在此情況下，所有失敗時於集區中舉行的作用中會議都會切換為限制模式，並且無法啟動新會議。
    
    IM 和會議會在更正失敗之後自動復原。

  - 指定使用 Microsoft Exchange Server 2013 整合，以使用 Exchange 2013 儲存封存資料，而不是設定個別的 SQL Server 資料庫來儲存 Lync Server 2013 封存資料。

  - 設定封存資料的清除選項。這包含指定何時清除封存的資料，可以是下列其中一項：
    
      - 在您指定的特定天數之後
    
      - 在匯出封存資料之後 (包括已上傳至 Exchange 的資料（如果您啟用 Microsoft Exchange 整合) ）。
    
    <div>
    

    > [!NOTE]  
    > 如果您啟用 Microsoft Exchange 整合，請清除駐留在 Exchange 2013 的使用者，並將其信箱置於 In-Place 保留狀態，由 Exchange 所控制。 只有在 Lync Server 檔案共用上儲存的會議檔案的唯一資格。 這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。

    
    </div>

預設不會啟用任何封存選項。 您可以使用 Lync Server 2013 控制台管理封存設定。

您可以指定下列封存設定：

  - **全域封存設定**。 此為預設的封存設定，可套用至您的整個部署。 它會在您部署 Lync Server 2013 時建立，而且根據預設，不會啟用封存功能。 您可以修改全域設定，但無法刪除它。 如果您針對設定選擇刪除選項，即會將全域設定重設為預設設定。

  - **網站封存設定**。您可以選擇性地為一或多個指定的網站設定封存，作法是針對個別網站建立和設定網站層級的封存設定。網站層級的封存設定只有在您建立它時才會存在。您可以修改或刪除任何網站層級的封存設定。網站層級的封存設定優先於全域設定，但僅適用於網站層級設定中指定的網站。例如，如果您在全域設定中僅針對 IM 啟用封存，並建立一個網站設定以針對 IM 和會議啟用封存，則只會針對該網站封存會議，而不會為貴組織的其餘部分封存會議。

  - **集區封存設定**。您可以選擇性地為一或多個指定的集區指定封存設定，作法是為個別集區建立和設定集區層級的設定。集區層級的封存設定只有在您建立它時才會存在。您可以修改和刪除任何集區層級的封存設定。集區層級的封存設定優先於全域設定，以及您可能已建立的任何網站封存設定。例如，如果您在全域設定中僅針對 IM 啟用封存，並建立一個網站層級的設定以針對該網站的 IM 和會議啟用封存，接著建立一個集區層級的設定以便僅針對 IM 啟用封存，則會針對網站的所有使用者封存 IM 與會議的通訊，但位於集區層級設定中指定之集區中的使用者例外。針對組織中所有的其他使用者，就只會針對 IM 啟用封存。

如需如何在部署封存時設定初始封存設定的詳細資訊，請參閱部署檔中的在 [Lync Server 2013](lync-server-2013-configuring-archiving-options.md) 中設定封存選項。 如需使用封存原則來啟用及停用部署後進行通訊的詳細資訊，請參閱 Operations 檔中的 [管理伺服器、網站及集區的 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 。

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>僅能在 Windows PowerShell 中使用的封存選項

使用 Lync Server 2013 管理命令介面，您可以使用 Cmdlet 來執行 Lync Server 2013 控制台中不可用的選項。 這些選項包括下列各項：

  - **封存重複的訊息**。 如需詳細資訊，請參閱作業文件中的 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 和 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)。

  - **匯出封存的資料**。 如需詳細資訊，請參閱 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>如何存取封存的資料？

存取封存的資料會根據儲存資料的地方而定：

  - **Microsoft Exchange storage**。 如果您選擇 Exchange 整合選項，Lync Server 會在 Exchange 2013 存放區中，針對所有位於 Exchange 2013 的使用者，以及其信箱置於 In-Place 保留狀態的使用者，在 Exchange 存放區中儲蓄內容。 封存的資料儲存在使用者信箱的 [可復原的專案] 資料夾中，該資料夾通常對使用者來說是無法看到的，而且只有具備 Exchange **探索管理** 角色的使用者可以搜尋。 Exchange 可在部署時，啟用同盟搜尋與探索，以及 SharePoint。 如需儲存在 Exchange 中之資料儲存、保留及探索的詳細資訊，請參閱 Exchange 2013 及 SharePoint 檔。

  - **Lync Server 儲存**。 如果您設定 Lync Server 2013 封存資料庫來儲存 Lync Server 資料，Lync Server 會將封存內容放在 Lync Server 封存資料庫中 (SQL Server 資料庫) ，以供任何不是位於 Exchange 2013 的使用者使用，也不會將其信箱置於 In-Place 保留狀態。 此資料是無法搜尋的，但可匯出為可使用其他工具搜尋的格式。 如需匯出儲存在封存資料庫中之資料的詳細資訊，請參閱操作檔中的 [從 Lync Server 2013 匯出封存的資料](lync-server-2013-exporting-archived-data.md) 。

如需有關 Lync Server 2013 和 Exchange 2013 如何共同運作的詳細資訊，請參閱支援檔 [中的 Exchange Server 和 SharePoint integration support In Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

