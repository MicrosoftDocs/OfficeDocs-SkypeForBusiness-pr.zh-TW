---
title: Lync Server 2013：存檔的運作方式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 097b40ef4194a618c090e0d67f73583d6aa427b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>存檔在 Lync Server 2013 中的運作方式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

Lync Server 2013 封存提供可協助您符合合規性需求的選項。 若要以最有效地符合貴組織需求的方式來實施及維護，您應該瞭解：

  - 您可以封存哪些資訊。

  - 如何在您的部署中啟用和停用封存。

  - 您可以設定的封存選項，以控制實施封存的方式。

<div>

## <a name="what-information-can-be-archived"></a>哪些資訊可以封存？

您可以封存下列內容類型：

  - 對等立即訊息

  - 會議（會議），這是多方立即訊息

  - 會議內容，包括上傳的內容（例如講義）及事件相關內容（例如加入、離開、上傳共用，以及在可見度中變更）

  - 在會議期間共用白板和投票

下列內容類型沒有封存：

  - 對等檔案傳輸

  - 對等立即訊息與會議的音訊/視頻

  - 對等立即訊息和會議的桌面與應用程式共用

Lync Server 也不封存持久的聊天交談。 若要封存持續聊天交談，您必須啟用並設定合規性服務，這是可使用 Microsoft Lync Server 2013、持久聊天伺服器部署的元件。 如需詳細資訊，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>我要如何開始使用存檔？

當您部署伺服器時，會在每個前端伺服器上自動安裝封存，但除非您設定存檔，否則不會啟用封存。 您設定的方式取決於您部署存檔的方式：

  - **使用 Microsoft Exchange 整合進行封存。** 如果您擁有託管于 Exchange 2013 的使用者，且其信箱已放在就地保留中，您可以選取將 Lync Server 2013 儲存空間與 Exchange 儲存體整合的選項。 如果您選擇 [Microsoft Exchange 整合] 選項，您可以使用 Exchange 2013 原則和設定來控制這些使用者的 Lync Server 2013 資料的存檔。

  - **使用 Lync Server 封存資料庫進行封存。** 如果您有非託管于 Exchange 2013 的使用者，或未將其信箱放在就地保留中的使用者，或者您不想針對部署中的任何或所有使用者使用 Microsoft Exchange 整合，就可以使用 SQL Server 部署 Lync Server 封存資料庫 儲存這些使用者的存檔資料。 在這種情況下，Lync Server 2013 封存原則和設定會判斷是否已啟用並執行封存。 若要使用 Lync Server 2013，您必須在拓撲中新增適當的 SQL Server 資料庫，然後發佈拓撲。

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>使用 Microsoft Exchange 整合時的存檔設定

如果您的使用者是駐留在 Exchange 2013 上，且其信箱已放在就地保留中，您可以選擇 [ **Microsoft Exchange 整合**] 選項（如本節稍後所述），以封存這些使用者的 Lync server 2013，然後使用 [Exchange 就地保留原則] 和 [設定]，以及 [Lync 伺服器設定] 控制這些使用者的歸檔，以控制下列各項：

  - 是否要封存 IM、會議或兩者。

  - 是否要為 Lync Server 部署實現重要模式。

  - 選取 [Microsoft Exchange 整合] 選項，即可使用 Exchange 2013 儲存已歸檔的資料。

此區段稍後會說明這些 Lync Server 2013 封存配置選項。 如需如何設定 Exchange 就地保留原則和設定以支援封存的相關資訊，請參閱 Exchange 2013 產品檔。

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>使用 Lync Server 封存資料庫儲存空間時的存檔設定

如果您想要使用 Lync Server 封存資料庫（使用 SQL Server 資料庫）來為您部署中的任何使用者封存資料，您可以設定 Lync Server 封存原則來控制是否已針對這些使用者啟用封存功能。 在每個存檔原則中，您可以啟用或停用下列其中一項或兩項作業：

  - 內部通訊

  - 外部通訊

根據預設，在任何 Lync Server 存檔原則中，都不會針對內部通訊或外部通訊啟用封存。 您可以使用 Lync Server 2013 [控制台] 或在 Lync Server 2013 管理命令介面中使用 Cmdlet 來啟用和停用通訊。

Lync Server 2013 的歸檔原則包括下列各項：

  - **全域存檔原則**。 這是預設的存檔原則，且適用于整個部署。 它是在您部署 Lync Server 2013 時建立的，而且預設會停用內部與外部通訊的存檔。 您無法刪除此原則。 如果您選擇 [刪除] 選項，全域原則將重設為預設設定。

  - **網站歸檔原則**。 或者，您可以建立及設定網站的網站層級歸檔原則，以啟用或停用一或多個特定網站的封存。 當您建立網站層級歸檔原則時，預設不會啟用封存。 您可以刪除任何您建立的網站層級歸檔原則。 網站層級的歸檔原則會覆寫全域原則，但只適用于原則中指定的網站。 例如，如果您在全域原則中啟用內部和外部通訊的封存，並建立您在其中停用外部通訊封存的網站原則，則只有內部通訊會針對該網站進行歸檔。

  - **使用者歸檔原則**。 或者，您也可以為特定的使用者和使用者群組建立、設定及套用使用者層級歸檔原則，以啟用或停用一或多個特定使用者和使用者群組的封存。 當您建立使用者層級歸檔原則時，系統預設不會啟用封存。 您可以刪除您建立的任何使用者層級歸檔原則，而且您可以變更封存原則適用的使用者和使用者組。 使用者層級的歸檔原則會覆寫全域原則和任何網站原則，但只適用于已套用原則的使用者和使用者群組。 例如，如果您在全域原則中停用內部和外部通訊的封存，請建立網站層級原則，您可以在其中啟用內部和外部通訊的封存，然後建立您停用的使用者層級原則。針對外部通訊進行封存，除了針對您套用使用者層級原則的使用者之外，您還會針對所有網站使用者的外部與內部通訊歸檔通訊，只會封存內部通訊。

如需有關如何在部署存檔時設定初始封存原則的詳細資訊，請參閱在部署檔中設定[和指派 Lync Server 2013 中的存檔原則](lync-server-2013-configuring-and-assigning-archiving-policies.md)。 如需使用封存原則在部署後啟用和停用通訊的詳細資料，請參閱在作業檔中[管理 Lync Server 2013 內的內部和外部通訊](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。

<div>


> [!NOTE]  
> 如果您同時執行兩個 Lync Server 2013 封存資料庫並啟用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫 Lync Server 封存原則，但只適用于駐留在 Exchange 2013 且已將其信箱放在就地保留中的使用者. Lync 存檔只依賴 Microsoft Exchange 就地保留原則。



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>我有哪些選項可設定存檔？

除了使用原則以及啟用及停用封存之外，您還可以針對整個部署以及特定網站和池（您也可以）設定其他的存檔選項。 您可以使用一或多個存檔設定（可在 Lync Server 2013 的 [控制台] 中找到）來控制大部分的存檔選項，但也有另一個選項，只適用于使用 Lync Server 2013 管理命令介面的配置。

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 的 [控制台] 中提供的 [封存配置選項]

每個封存配置都提供下列選項：

全域層級設定是在您部署封存時自動建立，而且可以設定，但不能刪除。 如果您選取刪除全域設定的選項，設定就會重設為預設值。 您可以建立多個網站和池設定，搭配全域配置來控制存檔設定。 針對全域設定以及每個網站和池配置，您可以使用下列選項：

  - 停用 [封存]、[只針對立即訊息（IM）啟用封存]，或啟用 IM 與會議的存檔。

  - 設定在 Lync 伺服器失敗時封鎖 IM 和會議會話的 [關鍵模式]。 失敗包括下列各項：
    
      - **即時消息**。 Lync Server storage service 發生問題。 在此情況下，具有封存能力的使用者皆無法使用 IM。
    
      - **會議**。 失敗原因可能是無法使用檔案共用，或存放服務發生問題。 在此情況下，所有於失敗時間在集區中進行的會議，都會切換為限制模式，而且無法啟動新的會議。
    
    IM 和會議會在更正失敗之後自動復原。

  - 指定使用 Microsoft Exchange Server 2013 整合，以使用 Exchange 2013 儲存已歸檔的資料，而不是設定個別的 SQL Server 資料庫來儲存 Lync Server 2013 封存資料。

  - 針對存檔資料設定清除選項。 這包括指定何時清除封存的資料，這可能是下列其中一項：
    
      - 在您指定的天數之後
    
      - 匯出資料之後（包括已上傳至 Exchange 的資料），如果您啟用 Microsoft Exchange 整合，就會出現這種情況。
    
    <div>
    

    > [!NOTE]  
    > 如果您啟用 Microsoft Exchange 整合，請清除駐留在 Exchange 2013 的使用者，並將其信箱放在就地保留中，由 Exchange 控制。 唯一的認證是儲存在 Lync Server 檔案共用的會議檔案。 這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。

    
    </div>

根據預設，不會啟用任何存檔選項。 您可以使用 Lync Server 2013 [控制台] 管理封存配置。

您可以指定下列存檔設定：

  - **全域存檔**設定。 這是預設的存檔設定，且適用于整個部署。 它是在您部署 Lync Server 2013 時建立，而且預設不會啟用 [封存] 功能。 您可以修改全域設定，但無法將其刪除。 如果您選擇設定的 [刪除] 選項，全域設定就會重設為預設設定。

  - **網站封存配置**。 或者，您也可以透過建立及設定個別網站的網站層級封存設定，來設定一或多個特定網站的存檔。 網站層級的歸檔設定只有在您建立時才存在。 您可以修改或刪除任何網站層級的存檔設定。 網站層級的存檔設定會覆寫全域設定，但僅適用于網站層級設定中指定的網站。 例如，如果您只針對全域設定中的 IM 啟用 [封存]，並建立可讓 IM 與會議同時啟用存檔的網站設定，會議將只會封存給該網站，而不是貴組織的其餘部分。

  - **池存檔**設定。 或者，您也可以為個別的 [池] 建立和設定池層級設定，以指定一或多個特定資源池的存檔設定。 池層級的歸檔設定只有在您建立時才存在。 您可以修改並刪除任何池層級的存檔設定。 池層級的存檔設定會覆寫全域設定和您可能已建立的任何網站封存設定。 例如，如果您只針對全域設定中的 IM 啟用 [封存]，請建立網站層級設定，讓您為網站的 IM 和會議啟用封存，然後建立一層級設定，讓您只在其中啟用存檔IM，對於網站的所有使用者，除了駐留在池層級設定中指定的池中的使用者之外，還會針對該網站的所有使用者封存 IM 和會議的通訊。 針對貴組織中的所有其他使用者，只會針對 IM 啟用封存功能。

如需如何在部署存檔時設定初始封存配置的詳細資料，請參閱在部署檔中的[Lync Server 2013](lync-server-2013-configuring-archiving-options.md)中的 [設定封存選項]。 如需在部署後使用封存原則啟用和停用通訊的詳細資料，請參閱在作業檔中[針對貴組織、網站和池管理 Lync Server 2013 中的 [存檔](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)設定] 選項。

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>只能在 Windows PowerShell 中使用封存選項

使用 Lync Server 2013 管理命令介面，您可以使用 Cmdlet 來實現 Lync Server 2013 [控制台] 中不提供的選項。 這些選項包括下列各項：

  - 封存**重複的郵件**。 如需詳細資訊，請參閱作業檔中的[新 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration)和[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) 。

  - **匯出**封存的資料。 如需詳細資訊，請參閱[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>如何存取已歸檔的資料？

歸檔資料的存取權視資料的儲存位置而定：

  - **Microsoft Exchange 儲存空間**。 如果您選擇 [Exchange 整合] 選項，Lync Server 會在 Exchange 2013 存放區中針對所有託管于 Exchange 2013 的使用者，以及將其信箱放在就地保留中的使用者，將其存檔。 已歸檔的資料會儲存在使用者信箱可復原的專案資料夾中，對於使用者通常是不可見的，而且只有擁有 Exchange**探索管理**角色的使用者才能進行搜尋。 Exchange 可在已部署的情況下，與 SharePoint 一起啟用同盟搜尋與探索。 如需有關儲存在 Exchange 中之資料的儲存、保留和探索的詳細資訊，請參閱 Exchange 2013 和 SharePoint 檔。

  - **Lync Server 儲存空間**。 如果您設定 Lync Server 2013 封存資料庫以儲存 Lync Server 資料，Lync Server 會將存檔內容放在 Lync Server 封存資料庫（SQL Server 資料庫）中，以供未駐留在 Exchange 2013 的任何使用者使用，而且未將其信箱放在就地保留。 此資料是無法搜尋的，但可將其匯出為可使用其他工具搜尋的格式。 如需有關匯出儲存在歸檔資料庫中之資料的詳細資訊，請參閱在作業檔中[匯出 Lync Server 2013 的存檔資料](lync-server-2013-exporting-archived-data.md)。

如需有關 Lync Server 2013 與 Exchange 2013 共同運作方式的詳細資訊，請參閱可支援性檔中的[Lync server 2013 中的 Exchange Server 和 SharePoint 整合支援](lync-server-2013-exchange-and-sharepoint-integration-support.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

