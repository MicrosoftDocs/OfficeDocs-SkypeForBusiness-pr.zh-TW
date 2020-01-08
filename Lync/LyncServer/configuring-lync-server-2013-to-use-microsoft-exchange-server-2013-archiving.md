---
title: 將 Lync Server 2013 設定為使用 Microsoft Exchange Server 2013 歸檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3f8ab22ed23adbce2d6cbd6ccbf1f378476ff00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>將 Microsoft Lync Server 2013 設定為使用 Microsoft Exchange Server 2013 歸檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-24_

Microsoft Lync Server 2013 可讓系統管理員選擇將即時消息和網路會議記錄存檔至使用者的 Microsoft Exchange Server 2013 信箱，而不是 SQL Server 資料庫。 如果您啟用此選項，則會在使用者的信箱中，將 [文字] 寫入 [清除] 資料夾。 [清除] 資料夾是一個隱藏資料夾，位於 [可復原的專案] 資料夾中。 雖然此資料夾不適用於最終使用者，但資料夾是由 Exchange 搜尋引擎編制索引，而且可以使用 Exchange 信箱搜尋和/或 Microsoft SharePoint Server 2013 來探索。 由於資訊是儲存在 Exchange 就地保留功能所使用的同一個資料夾（負責封存電子郵件和其他 Exchange 通訊），因此系統管理員可以使用單一工具來搜尋所有存檔的電子通訊使用者名.

<div>


> [!IMPORTANT]  
> 若要完全停用 Lync 交談的封存，您也必須停用 Lync 交談記錄。 如需詳細資訊，請參閱下列主題：<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 中內部與外部通訊</A>的封存、<A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">新 CsClientPolicy</A>及<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">CsClientPolicy</A>。



</div>

若要將檔封存至 Exchange 2013，您必須先在兩個伺服器之間設定伺服器對伺服器的驗證。 在進行伺服器對伺服器驗證之後，您就可以在 Microsoft Lync Server 2013 中執行下列工作（請注意，根據您的設定和設定而定，您可能不需要完成這些工作）：

1.  修改您的 Lync Server 封存設定設定以啟用 Exchange 封存。 所有部署都必須執行此步驟。

2.  針對您的使用者啟用內部與/或外部通訊的封存。 所有部署都必須執行此步驟。

3.  針對每位使用者設定 ExchangeArchivingPolicy 屬性。 只有在 Lync Server 和 Exchange 位於不同的林中時，才需要執行此步驟。

<div>

## <a name="step-1-enabling-exchange-archiving"></a>步驟1：啟用 Exchange 封存

Lync Server 中的封存主要是使用 [存檔設定] 進行管理。 當您安裝 Lync Server 2013 時，系統會自動為您提供單一、全域集合的這些設定。 （系統管理員可以選擇在網站範圍中建立新的存檔設定集合）。根據預設，全域設定中不會啟用封存，也不會在這些設定中啟用 Exchange 封存。 若要使用 Exchange 封存管理員，必須在這些配置設定中設定 EnableArchiving 和 EnableExchangeArchiving 屬性。 EnableArchiving 屬性可以設定為三個可能值的其中之一：

  - [**無**]。 封存已停用。 此為預設值。 如果 EnableArchiving 設定為 [無]，則不會將任何檔案封存在您的 Lync Server 封存資料庫或 Exchange 2013 中。

  - **ImOnly**。 只封存立即訊息記錄。 如果啟用 Exchange 封存，這些記錄將會在 Exchange 2013 中封存。 如果 Exchange 封存停用，這些記錄將會封存至 Lync Server。

  - **ImAndWebConf**。 立即訊息記錄和網路會議記錄都已歸檔。 如果啟用 Exchange 封存，這些記錄將會在 Exchange 2013 中封存。 如果 Exchange 封存停用，這些記錄將會封存至 Lync Server。

EnableExchangeArchiving 屬性是布林值：將 EnableExchangeArchiving 設定為 True （$True）以啟用 Exchange 封存，或將 EnableExchangeArchiving 設定為 False （$False）來停用 Exchange 封存。 例如，這個命令可讓您封存立即訊息記錄，同時也能啟用 Exchange 封存：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

若要停用 Exchange 封存，請使用類似下列的命令來啟用立即訊息歸檔，但會停用 Exchange （換句話說，文字會歸檔至 Lync Server）：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> 如果 EnableArchiving 屬性設為 [無]，則 Lync Server 根本不會封存立即訊息和網路會議記錄。 在這種情況下，伺服器會直接忽略針對 EnableExchangeArchiving 設定的值。



</div>

您也可以使用 Lync Server [控制台] 啟用（或停用） Exchange 封存。 若要這樣做，請完成下列程式：

1.  在 [控制台] 中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

2.  在 [封存**配置**] 索引標籤上，按兩下要修改的封存設定集合（例如，**全域**集合）。

3.  在 [**編輯封存設定**] 窗格中，按一下 [封存**設定**] 下拉式清單，然後選取 [封存**im 會話**] （[只封存立即訊息會話]），或是 [封存**im 和網路**會議] 會話（以封存立即訊息和網路會議會話）。

4.  選擇要封存的專案之後，請選取 [ **Exchange Server 整合**] 核取方塊以啟用 Exchange 封存。 若要停用 Exchange 封存，請清除此核取方塊。

<div>


> [!NOTE]  
> 如果將 [封存]<STRONG>設定</STRONG>設為 [<STRONG>停</STRONG>用封存]，就無法使用 [ <STRONG>Exchange Server 整合</STRONG>] 核取方塊。 您必須先啟用存檔，然後啟用 Exchange 封存。



</div>

如果 Lync Server 2013 和 Exchange 2013 位於同一個林中，則為個別使用者進行封存（或至少針對在 Exchange 2013 中有電子郵件帳戶的使用者），是使用 Exchange 就地保留原則來管理。 如果您的使用者是以舊版 Exchange 為宿主，則會使用 Lync Server 封存原則管理這些使用者的存檔。 請注意，只有 Exchange 2013 帳戶的使用者才能將其 Lync 記錄存檔至 Exchange。

如果 Lync Server 2013 和 Exchange 2013 位於不同的林中，則會透過設定每個個別使用者帳戶的 ExchangeArchivingPolicy 屬性來管理針對個別使用者進行的存檔。 如需詳細資訊，請參閱步驟3。

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步驟2：啟用內部及/或外部通訊的存檔

在您啟用封存功能之後（以及 Exchange 封存）之後，您必須修改適當的存檔原則，以確保使用者會話已實際封存。 請注意，只要啟用封存（步驟1），就不會讓 Lync Server 開始封存立即訊息和網路會議記錄。 相反地，您必須使用封存原則來啟用內部及/或外部封存。 當您安裝 Lync Server 2013 時，您也會安裝單一、全域存檔策略，其中包含兩個屬性：

  - **ArchiveInternal**。 當設定為 True （$True）時，表示只會封存涉及在貴組織中擁有 Active Directory 帳戶之使用者的內部通訊會話。

  - **ArchiveExternal**。 當設定為 True （$True）時，表示內部通訊會話（至少有一個使用者在貴組織中沒有 Active Directory 帳戶的會話）將會封存。

根據預設，這些屬性值會設定為 False，表示不會封存內部或外部通訊會話。 若要修改全域原則，您可以使用 Lync Server 管理命令介面和 CsArchivingPolicy Cmdlet。 這個命令可讓您同時存檔內部和外部通訊會話：

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

或者，您也可以使用新的 CsArchivingPolicy，在網站範圍或每個使用者的範圍內建立新的原則。 例如，這個命令會建立一個名為 RedmondArchivingPolicy 的新的每使用者存檔策略：

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

如果您建立每個使用者的原則，您必須將該原則指派給適當的使用者。 例如：

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

您也可以使用 Lync Server [控制台] 來管理歸檔原則。 在 [控制台] 中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。 若要修改現有的原則，請按兩下原則（例如全域），然後在 [**編輯封存原則**] 窗格中，選取或清除 [封存**內部通訊**] 和 [封存**外部通訊**] 核取方塊（視需要）。 若要建立新的存檔原則，請按一下 [**新增**]，然後選取 [**網站原則**] 或 [**使用者原則**]。 如果您建立新的使用者策略，您必須存取適當的使用者帳戶（從 [**使用者**] 索引標籤），並將這些使用者指派給新的原則。

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步驟3：設定 ExchangeArchivingPolicy 屬性

如果 Lync Server 2013 與 Exchange 2013 位於不同的林中，則在 [封存設定] 設定中只啟用 Exchange 封存是不夠的。這不會導致立即訊息和網路會議記錄在 Exchange 中進行封存。 相反地，您也必須在每個相關的 Lync Server 使用者帳戶上設定 ExchangeArchivingPolicy 屬性。 這個屬性可以設定為四個可能值的其中之一：

1.  狀態. 指出將根據針對使用者的 Exchange 信箱設定的就地保留設定來存檔;如果未在使用者的信箱上啟用就地保留，使用者將會在 Lync Server 中將其訊息和網路會議記錄存檔。

2.  **UseLyncArchivingPolicy**。 表示使用者的立即訊息和網路會議記錄應該在 Lync Server 上歸檔，而不是在 Exchange 中。

3.  **NoArchiving**。 表示使用者的立即訊息和網路會議記錄根本不應進行封存。 請注意，此設定會覆寫指派給使用者的任何 Lync Server 封存原則。

4.  **ArchivingToExchange**。 表示無論是否已將（或尚未）指派給使用者信箱的就地保留設定，都應該將使用者的立即訊息和網路會議記錄歸檔至 Exchange。

例如，若要設定使用者帳戶，讓立即訊息和網路會議記錄都能歸檔到 Exchange，您可以使用與 Lync Server 管理命令介面類別似的命令：

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

如果您想要為一組使用者設定相同的歸檔原則（例如，所有使用者都駐留在指定的註冊機構池中），您可以使用類似以下的命令：

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

請注意，您必須使用 Lync Server 管理命令介面（與 Windows PowerShell），才能設定 ExchangeArchivingPolicy 屬性的值。 在 Lync Server [控制台] 中不會向管理員公開這個屬性。

如果您想要查看已獲指派特定歸檔原則之所有使用者的清單，您可以使用類似下列的命令，這會傳回已設定 ExchangeArchivingPolicy 屬性的所有使用者的 Active Directory 顯示名稱。取消初始化：

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

同樣地，這個命令會傳回沒有 ExchangeArchivingPolicy 屬性設定為 UseLyncArchivingPolicy 的使用者的顯示名稱：

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

