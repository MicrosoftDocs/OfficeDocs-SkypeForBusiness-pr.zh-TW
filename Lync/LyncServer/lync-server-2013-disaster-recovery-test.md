---
title: Lync Server 2013：災難修復測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2d36ec6ad1afb8c41c7c5f614e90e03ce4d9282
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528950"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013 中的嚴重損壞修復測試

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-26_

對 Lync Server 2013 集區伺服器執行系統復原，以測試您已記錄的嚴重損壞修復程式。 這項測試會模擬一部伺服器的完整硬體故障，並協助保證資源、計畫及資料可用於復原。 嘗試每月旋轉測試的焦點，使組織每次測試不同伺服器或其他裝置的失敗。

請注意，組織執行嚴重損壞修復測試的排程會有所不同。 不會忽視或忽略嚴重損壞修復測試，這一點很重要。

<div>


將 Lync Server 2013 拓撲、原則及設定設定匯出至檔案。 除此之外，您也可以使用此檔案在升級、硬體故障或其他問題導致資料遺失的情況下，將此資訊還原至中央管理存放區。

將 Lync Server 2013 拓撲、原則及設定設定匯入中央管理存放區或本機電腦，如下列命令所示：

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

若要備份 Lync Server 2013 資料，請執行下列動作：

  - 使用標準 SQL Server 備份程式備份 RTC 和 LCSLog 資料庫，以將資料庫轉儲至檔案或磁帶轉儲裝置。

  - 使用協力廠商備份應用程式將資料備份至檔案或磁帶。

  - 使用 Export-CsUserData Cmdlet 來建立整個 RTC 資料庫的 XML 匯出。

  - 使用檔案系統備份或協力廠商備份會議內容和合規性記錄檔。

  - 使用 Export-CsConfiguration 命令列工具備份 Lync Server 2013 設定。

容錯移轉程式中的第一個步驟包括將使用者從生產集區強制移至嚴重損壞修復集區。

這將會強制移動，因為實際生產集區無法接受使用者重新安置。

除了 RTC SQL 資料庫上的記錄更新之外，Lync Server 2013 移動使用者程式也會變更使用者帳戶物件上的屬性。

您可以透過下列兩個程式還原此資料：

  - 使用標準 SQL server 還原程式，或使用協力廠商備份/還原公用程式，可以從生產 SQL Server 從原始備份轉儲裝置還原 RTC 資料庫。

  - 您可以使用由實際執行 SQL Server 匯出的 XML 檔案，將使用者連絡人資料還原為 DBIMPEXP.exe 公用程式。

還原此資料之後，使用者就能有效地連線至嚴重損壞修復 Lync Server 2013 集區，並照常運作。

若要讓使用者能夠連線至嚴重損壞修復 Lync Server 2013 集區，將需要 DNS 記錄變更。

使用的自動設定和 DNS SRV 記錄，用戶端將會參考實際執行的 Lync Server 2013 集區：

  - SRV： \_ sip。 \_Tls。\<domain\> /CNAME： SIP。\<domain\>

  - CNAME： SIP。\<domain\> /cvc-pool-1.\<domain\>

若要協助容錯移轉，必須更新此 CNAME 記錄，以參考 DROCSPool FQDN：

  - CNAME： SIP。\<domain\> /DROCSPool.\<domain\>

  - Sip。\<domain\>

  - Av。\<domain\>

  - webconf.\<domain\>

  - OCSServices.\<domain\>

<div>


> [!IMPORTANT]  
> 如需詳細的系統管理和管理程式，請參閱 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">備份及還原 Lync Server 2013</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Lync Server 2013 中的備份和高可用性 Cmdlet](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[備份及還原 Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[管理 Lync Server 2013 災難修復、高可用性及備份服務](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

