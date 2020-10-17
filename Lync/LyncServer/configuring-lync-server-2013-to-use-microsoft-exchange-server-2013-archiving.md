---
title: 設定 Lync Server 2013 以使用 Microsoft Exchange Server 2013 封存
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
ms.openlocfilehash: b6f557c95b9bf706b3a38b51bdbea4fea156b314
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503160"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>設定 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 封存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-24_

Microsoft Lync Server 2013 可讓管理員選擇將立即訊息和 Web 會議記錄封存到使用者的 Microsoft Exchange Server 2013 信箱，而不是 SQL Server 資料庫。 若您啟用了此選項，系統就會將記錄寫入使用者信箱的「清理」資料夾。 「清理」資料夾是「可復原項目」資料夾中的隱藏資料夾。 雖然此資料夾對使用者看不見，但資料夾是由 Exchange 搜尋引擎編制索引，而且可以使用 Exchange 信箱搜尋和/或 Microsoft SharePoint Server 2013 來探索。 因為資訊儲存在 Exchange In-Place 保留功能所使用的相同資料夾中 (負責封存電子郵件和其他 Exchange 通訊) ，所以系統管理員可以使用單一工具來搜尋所有為使用者封存的電子通訊。

<div>


> [!IMPORTANT]  
> 若要完全停用 Lync 交談的封存，您也必須停用 Lync 交談歷程記錄。 如需詳細資訊，請參閱下列主題：在 Lync Server 2013、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>及<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A><A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">中管理內部和外部通訊</A>的封存。



</div>

若要將記錄封存至 Exchange 2013，您必須先設定兩部伺服器間的伺服器對伺服器驗證。 在進行伺服器對伺服器驗證之後，您可以在 Microsoft Lync Server 2013 中執行下列工作 (請注意，視您的設定和設定而定，您可能不需要完成下列所有工作) ：

1.  修改 Lync Server 封存設定設定，以啟用 Exchange 封存。 所有部署都必須進行此步驟。

2.  針對使用者的內部及/或外部通訊，啟用封存。 所有部署都必須進行此步驟。

3.  針對每個使用者設定 ExchangeArchivingPolicy 屬性。 只有在 Lync Server 和 Exchange 位於不同樹系中時，才需要執行此步驟。

<div>

## <a name="step-1-enabling-exchange-archiving"></a>步驟1：啟用 Exchange 封存

Lync Server 中的封存主要是使用封存設定設定來管理。 當您安裝 Lync Server 2013 時，系統會自動為您提供這些設定的單一全域集合。  (管理員可以選擇性地在網站範圍建立新的封存設定集合。 ) 依預設，全域設定中不會啟用封存，也不會在這些設定中啟用 Exchange 封存。 若要使用 Exchange 封存管理員，必須設定這些設定中的 EnableArchiving 和 EnableExchangeArchiving 屬性。 EnableArchiving 屬性可設定為下列三個可能值之一：

  - **None**。 封存已停用。 這是預設值。 如果 EnableArchiving 設定為 None，則不會在 Lync Server 封存資料庫或 Exchange 2013 中封存任何專案。

  - **ImOnly**。 只封存立即訊息記錄。 如果啟用 Exchange 封存，這些記錄會在 Exchange 2013 中封存。 如果停用 Exchange 封存，則這些記錄會封存至 Lync Server。

  - **ImAndWebConf**。 立即訊息記錄和 Web 會議記錄皆已封存。 如果啟用 Exchange 封存，這些記錄會在 Exchange 2013 中封存。 如果停用 Exchange 封存，則這些記錄會封存至 Lync Server。

EnableExchangeArchiving 屬性為 Boolean 值：將 EnableExchangeArchiving 設定為 True ($True) 啟用 Exchange 封存，或將 EnableExchangeArchiving 設定為 False ($False) 以停用 Exchange 封存。 例如，此命令可啟用立即訊息記錄的封存，也可啟用 Exchange 封存：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

若要停用 Exchange 封存，請使用類似下列的命令，以啟用立即訊息封存，但會停用封存至 Exchange (換句話說，將會將記錄封存至 Lync Server) ：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> 如果 EnableArchiving 屬性設定為 [無]，則 Lync Server 根本不會封存立即訊息和 Web 會議記錄。 在這種情況下，伺服器會忽略 EnableExchangeArchiving 所設定的值。



</div>

您也可以使用 Lync Server 控制台， (或停用) 來啟用 Exchange 封存。 若要執行這項作業，請完成下列程序：

1.  在控制台中，按一下 [監控和封存]****，然後按一下 [封存組態]****。

2.  在 [封存組態]**** 索引標籤中，按兩下要修改的封存設定集合 (例如，[全域]**** 集合)。

3.  在 [編輯封存設定]**** 窗格中，按一下 [封存設定]**** 下拉式清單，然後選取 [封存 IM 工作階段]**** (若只要封存立即訊息工作階段) 或 [封存 IM 和 Web 會議工作階段]**** (若要封存立即訊息和 Web 會議工作階段)。

4.  選擇要封存的專案後，請選取 [ **Exchange Server 整合** ] 核取方塊以啟用 Exchange 封存。 若要停用 Exchange 封存，請清除此核取方塊。

<div>


> [!NOTE]  
> 若 [封存設定]<STRONG></STRONG> 是設為 [停用封存]<STRONG></STRONG>，就無法使用 [Exchange 伺服器整合]<STRONG></STRONG> 核取方塊。 您必須先啟用封存，然後啟用 Exchange 封存。



</div>

如果 Lync Server 2013 和 Exchange 2013 位於相同樹系中，則會為個別使用者封存 (，或至少針對在 Exchange 2013) 上具有電子郵件帳戶的使用者，是使用 Exchange In-Place 保留原則來管理。 如果您擁有位於舊版 Exchange 的使用者，則會使用 Lync Server 封存原則來管理那些使用者的封存。 請注意，只有在 Exchange 2013 上具有帳戶的使用者才能將其 Lync 記錄封存為 Exchange。

如果 Lync Server 2013 和 Exchange 2013 位於不同的樹系中，則會透過設定個別使用者帳戶的 ExchangeArchivingPolicy 屬性來管理個別使用者的封存。 請參閱「步驟 3」以了解詳細資訊。

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步驟 2：啟用內部及/或外部通訊的封存

在您啟用封存 (和 Exchange 封存) 之後，您必須修改適當的封存原則，以確保實際封存使用者會話。 請注意，只要啟用封存 (步驟 1) 不會導致 Lync Server 開始封存立即訊息和 Web 會議記錄。 相反地，您必須使用封存原則來啟用內部及（或）外部封存。 當您安裝 Lync Server 2013 時，您也會安裝單一的全域封存原則，其中包含兩個屬性：

  - **ArchiveInternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (僅涉及組織中具備 Active Directory 帳戶之使用者的工作階段)。

  - **ArchiveExternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (涉及組織中至少有一名具備 Active Directory 帳戶之使用者的工作階段)。

根據預設，這兩個選項值都會設為 False，亦即不論內部或外部通訊工作階段都不會受到封存。 若要修改全域原則，您可以使用 Lync Server 管理命令介面和 Set-CsArchivingPolicy Cmdlet。 此命令可啟用內部和外部通訊工作階段的封存：

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

您也可以在網站範圍或個別使用者範圍，使用 New-CsArchivingPolicy 來建立新的原則。例如，此命令會建立名為 RedmondArchivingPolicy 的新個別使用者封存原則：

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

若您要建立個別使用者的原則，您就需要將該原則指派給適當的使用者。例如：

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

您也可以使用 Lync Server 控制台來管理封存原則。 在控制台中，按一下 [監控和封存]****，然後按一下 [封存原則]****。 若要修改現有的原則，按兩下原則 (例如：全域)，然後在 [編輯封存原則]**** 窗格中，視需要選取或清除 [封存內部通訊]**** 和 [封存外部通訊]**** 核取方塊。 若要建立新的封存原則，請按一下 [ **新增** ]，然後選取 [ **網站原則** ] 或 [ **使用者原則**]。 若您建立新的使用者原則，接著就必須存取適當的使用者帳戶 (從 [使用者]**** 索引標籤)，然後再將新的原則指派給這些使用者。

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步驟 3：設定 ExchangeArchivingPolicy 屬性

如果 Lync Server 2013 和 Exchange 2013 位於不同的樹系中，則在封存設定設定中只啟用 Exchange 封存是不夠的。這不會導致立即訊息和 Web 會議記錄在 Exchange 中封存。 相反地，您也必須在每個相關的 Lync Server 使用者帳戶上設定 ExchangeArchivingPolicy 屬性。 您可將此屬性設為下列四個可能值之一：

1.  初始 化。 表示封存會根據使用者的 Exchange 信箱所設定的 In-Place 保留設定而定;如果使用者的信箱尚未啟用 In-Place [保留]，使用者將會在 Lync Server 中封存其郵件和 Web 會議記錄。

2.  **UseLyncArchivingPolicy**。 表示使用者的立即訊息和 Web 會議記錄應該在 Lync Server 中封存，而不是在 Exchange 中封存。

3.  **NoArchiving**。 表示使用者的立即訊息和 Web 會議記錄根本不應該封存。 請注意，此設定會覆寫指派給使用者的任何 Lync Server 封存原則。

4.  **ArchivingToExchange**。 指出使用者的立即訊息和 Web 會議記錄應該封存至 Exchange，不論 (或尚未將) 指派給使用者信箱的 In-Place 保留設定。

例如，若要設定使用者帳戶，使立即訊息和 Web 會議記錄永遠封存至 Exchange，您可以使用來自 Lync Server 管理命令介面的類似如下的命令：

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

若您想針對群組使用者 (例如，所有位於特定登錄器集區的使用者) 設定相同的封存原則，可使用類似下列的命令：

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

請注意，您必須使用 Lync Server 管理命令介面 (和 Windows PowerShell) 才能設定 ExchangeArchivingPolicy 屬性的值。 此屬性不會向 Lync Server 控制台中的系統管理員公開。

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

