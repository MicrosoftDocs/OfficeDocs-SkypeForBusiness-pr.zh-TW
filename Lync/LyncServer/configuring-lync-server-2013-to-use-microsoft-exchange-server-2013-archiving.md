---
title: 設定 Lync Server 2013 使用 Microsoft Exchange Server 2013 封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85a9a1d035994c143336abc83312fb56f67b927d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>設定 Microsoft Lync Server 2013 使用 Microsoft Exchange Server 2013 封存

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-06-24_

Microsoft Lync Server 2013 可讓系統管理員選擇讓立即訊息和 Web 會議記錄封存至使用者的 Microsoft Exchange Server 2013 信箱，而不是 SQL Server 資料庫。 若您啟用了此選項，系統就會將記錄寫入使用者信箱的「清理」資料夾。 「清理」資料夾是「可復原項目」資料夾中的隱藏資料夾。 雖然使用者看不到這個資料夾、 資料夾由 Exchange 搜尋引擎編製索引，而且可以找到使用 Exchange 信箱搜尋和/或 Microsoft SharePoint Server 2013。 因為 Exchange 就地保留功能 （負責封存電子郵件和其他 Exchange 通訊） 所使用的相同資料夾中儲存的資訊，系統管理員可以使用單一的工具來搜尋所有電子通訊封存使用者。

<div>


> [!IMPORTANT]  
> 若要完全停用封存的 Lync 交談，您必須也停用 Lync 交談歷程記錄。 如需詳細資訊，請參閱下列主題：<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 中的內部和外部通訊的封存</A>、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-csclientpolicy</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-csclientpolicy</A>。



</div>

若要封存至 Exchange 2013 的記錄您必須首先設定兩部伺服器之間的伺服器對伺服器驗證。 伺服器對伺服器驗證已經準備就緒之後您可以再執行 Microsoft Lync Server 2013 （請注意，根據您的安裝和設定，您可能不需要完成這些工作的所有） 中的下列工作：

1.  啟用 Exchange 封存藉由修改 Lync Server 封存組態設定。 所有部署都必須進行此步驟。

2.  針對使用者的內部及/或外部通訊，啟用封存。 所有部署都必須進行此步驟。

3.  針對每個使用者設定 ExchangeArchivingPolicy 屬性。 此步驟只需要在 Lync Server 和 Exchange 位於不同樹系中。

<div>

## <a name="step-1-enabling-exchange-archiving"></a>步驟 1： 啟用 Exchange 封存

使用封存組態設定主要管理 Lync Server 中的封存。 當您安裝 Lync Server 2013 會自動獲得這些設定的單一、 全域集合。 （系統管理員可以選擇性地建立新的封存設定集合在網站範圍）。根據預設，全域設定中，在未啟用封存也不 Exchange 封存啟用這些設定。 若要使用 Exchange 封存系統管理員必須設定 EnableArchiving 和 EnableExchangeArchiving 屬性在這些組態設定。 EnableArchiving 屬性可設定為下列三個可能值之一：

  - **無**。 已停用封存。 這是預設值。 如果 EnableArchiving 設為 None，然後執行任何動作將會封存的 Lync Server 封存資料庫中的任一種或 Exchange 2013 中。

  - **ImOnly**。 僅限立即訊息記錄會封存。 如果已啟用 Exchange 封存這些記錄會封存在 Exchange 2013。 如果 Exchange 封存已停用這些記錄會封存至 Lync Server。

  - **ImAndWebConf**。 已封存立即訊息記錄和 Web 會議記錄。 如果已啟用 Exchange 封存這些記錄會封存在 Exchange 2013。 如果 Exchange 封存已停用這些記錄會封存至 Lync Server。

EnableExchangeArchiving 屬性是布林值： 設定為 True ($True) 來啟用 Exchange 封存或設定 EnableExchangeArchiving EnableExchangeArchiving 設為 False ($False) 若要停用 Exchange 封存。 例如，此命令啟用封存的立即訊息的記錄，並也可讓 Exchange 封存：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

若要停用 Exchange 封存，請使用類似下列項目，可啟用立即訊息封存，但會停用封存至 Exchange 命令 （也就是說，記錄會封存至 Lync Server）：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> 如果 EnableArchiving 屬性設為 [無然後 Lync 伺服器將不封存立即訊息和 Web 會議記錄所有。 在這種情況下，伺服器會忽略 EnableExchangeArchiving 所設定的值。



</div>

Exchange 封存也可啟用 （或已停用） 使用 Lync Server Control Panel。 若要執行這項作業，請完成下列程序：

1.  在控制台中，按一下 [監控和封存]****，然後按一下 [封存組態]****。

2.  在 [封存組態]**** 索引標籤中，按兩下要修改的封存設定集合 (例如，[全域]**** 集合)。

3.  在 [編輯封存設定]**** 窗格中，按一下 [封存設定]**** 下拉式清單，然後選取 [封存 IM 工作階段]**** (若只要封存立即訊息工作階段) 或 [封存 IM 和 Web 會議工作階段]**** (若要封存立即訊息和 Web 會議工作階段)。

4.  選擇之後要封存的項目，選取 [ **Exchange Server 整合**] 核取方塊以啟用 Exchange 封存]。 若要停用 Exchange 封存，請清除此核取方塊。

<div>


> [!NOTE]  
> 若 [封存設定]<STRONG></STRONG> 是設為 [停用封存]<STRONG></STRONG>，就無法使用 [Exchange 伺服器整合]<STRONG></STRONG> 核取方塊。 您必須啟用封存的第一個，然後啟用 [Exchange 封存。



</div>

如果 Lync Server 2013 和 Exchange 2013 都位於相同的樹系，然後針對個別使用者封存 （或是至少具有電子郵件的使用者帳戶在 Exchange 2013） 的管理方式使用 Exchange 就地保留原則。 如果您有位於舊版的 Exchange 然後封存這些使用者的使用者將受使用 Lync Server 封存原則。 請注意，只具有 Exchange 2013 的帳戶的使用者可能會有封存至 Exchange 其 Lync 文稿。

如果 Lync Server 2013 和 Exchange 2013 都位於不同樹系，然後針對個別使用者封存的管理方式設定 ExchangeArchivingPolicy 屬性的每個個別的使用者帳戶。 請參閱「步驟 3」以了解詳細資訊。

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步驟 2：啟用內部及/或外部通訊的封存

已啟用封存 （及 Exchange 封存後） 然後您必須修改適當的封存原則，以確保已實際上封存的使用者工作階段。 請注意，只啟用 [封存 (步驟 1) 不會導致 Lync Server 以開始封存立即訊息和 Web 會議記錄。 相反地，您必須使用封存原則以啟用內部及/或外部封存。 當您安裝 Lync Server 2013 還安裝單一時，全域封存原則包含兩個屬性：

  - **ArchiveInternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (僅涉及組織中具備 Active Directory 帳戶之使用者的工作階段)。

  - **ArchiveExternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (涉及組織中至少有一名具備 Active Directory 帳戶之使用者的工作階段)。

根據預設，這兩個選項值都會設為 False，亦即不論內部或外部通訊工作階段都不會受到封存。 若要修改全域原則，您可以使用 Lync Server 管理命令介面和 Set-csarchivingpolicy cmdlet。 此命令可啟用內部和外部通訊工作階段的封存：

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

您也可以在網站範圍或個別使用者範圍，使用 New-CsArchivingPolicy 來建立新的原則。例如，此命令會建立名為 RedmondArchivingPolicy 的新個別使用者封存原則：

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

若您要建立個別使用者的原則，您就需要將該原則指派給適當的使用者。例如：

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

封存原則也可以使用 Lync Server Control Panel 管理。 在控制台中，按一下 [監控和封存]****，然後按一下 [封存原則]****。 若要修改現有的原則，按兩下原則 (例如：全域)，然後在 [編輯封存原則]**** 窗格中，視需要選取或清除 [封存內部通訊]**** 和 [封存外部通訊]**** 核取方塊。 若要建立新的封存原則，按一下 [**新增**]，然後選取**網站原則**或**使用者原則**。 若您建立新的使用者原則，接著就必須存取適當的使用者帳戶 (從 [使用者]**** 索引標籤)，然後再將新的原則指派給這些使用者。

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步驟 3：設定 ExchangeArchivingPolicy 屬性

如果 Lync Server 2013 和 Exchange 2013 位於不同樹系中則不足夠只啟用 Exchange 封存中的封存組態設定;不會造成立即訊息和 Web 會議記錄在 Exchange 封存中。 相反地，您也必須在每個相關的 Lync Server 使用者帳戶上設定 ExchangeArchivingPolicy 屬性。 您可將此屬性設為下列四個可能值之一：

1.  未初始化。 會指出，封存會根據使用者的 Exchange 信箱; 設定為 「 就地保留設定如果原有範圍暫止不上已啟用使用者的信箱則使用者將會有他/她訊息和 Web 會議記錄封存的 Lync 伺服器中。

2.  **為 UseLyncArchivingPolicy**。 會指出該使用者的立即訊息和 Web 會議記錄應該封存 Lync Server，而非 Exchange 中。

3.  **NoArchiving**。 會指出該使用者的立即訊息和 Web 會議記錄應該不會封存所有。 請注意，此設定會覆寫任何 Lync Server 封存原則指派給使用者。

4.  **ArchivingToExchange**。 會指出使用者的立即訊息和 Web 會議記錄應該封存至 Exchange 就地保留設定不論有 （或不具有） 已指派給使用者的信箱。

例如，若要設定的使用者帳戶，以便立即訊息和 Web 會議記錄一律封存至 Exchange，您可以使用類似從 Lync Server 管理命令介面命令：

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

若您想針對群組使用者 (例如，所有位於特定登錄器集區的使用者) 設定相同的封存原則，可使用類似下列的命令：

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

請注意，您必須使用 Lync Server 管理命令介面 （和 Windows PowerShell），才能設定 ExchangeArchivingPolicy 屬性的值。 此屬性不會公開給 Lync Server Control Panel 中的系統管理員。

若您要檢視已指派特定封存原則之所有使用者的清單，您就可以使用類似下列的命令，即可傳回已將 ExchangeArchivingPolicy 屬性設為 Uninitialized 之所有使用者的 Active Directory 顯示名稱：

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

同樣地，此命令會傳回已將 ExchangeArchivingPolicy 屬性設為 UseLyncArchivingPolicy 之使用者的顯示名稱：

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

