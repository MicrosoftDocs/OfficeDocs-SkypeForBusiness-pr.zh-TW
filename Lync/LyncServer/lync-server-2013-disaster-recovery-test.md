---
title: Lync Server 2013： 嚴重損壞修復測試
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
ms.openlocfilehash: c0b274d933fbb1c9f47b219a492403bd1c5f58d5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013 中的嚴重損壞修復測試

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-01-26_

執行系統修復 Lync Server 2013 集區伺服器來測試您所記錄的災害復原程序。 這項測試將模擬一部伺服器，完整的硬體失敗，並可協助確保資源、 計劃及資料都可用於復原。 請試著旋轉測試每個月的焦點，以便您的組織測試不同伺服器或其他設備每次失敗。

請注意，依據組織執行嚴重損壞修復測試排程而有所不同。 它是非常重要的嚴重損壞修復測試不會略過或是忽略。

<div>


將 Lync Server 2013 拓撲、 原則和設定匯出至檔案。 除此之外，這個檔案然後可以用來還原中央管理存放區的這項資訊之後升級、 硬體故障、 或某些其他問題，會導致資料遺失。

匯入您的 Lync Server 2013 拓撲、 原則和設定中央管理存放區，或本機電腦的下列命令所示：

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

若要備份實際執行 Lync Server 2013 資料：

  - 備份 RTC 和 LCSLog 資料庫使用標準的 SQL Server 備份程序，以將資料庫檔案或磁帶時付出的傾印裝置傾印。

  - 使用協力廠商備份應用程式備份資料，檔案或到磁帶。

  - 使用 Export-csuserdata cmdlet 來建立 XML 匯出的整個 RTC 資料庫。

  - 使用檔案系統備份或協力廠商備份會議內容及規範的記錄檔。

  - 使用 Export-csconfiguration 命令列工具來備份 Lync Server 2013 設定。

容錯移轉程序的第一個步驟包含實際執行集區的災害復原集區的使用者以強制的移動。

這將會以強制的移動，因為實際執行集區無法使用接受使用者重新配置。

使用 Lync Server 2013 移動使用者程序實際上就是使用者帳戶物件上的 RTC SQL 資料庫的記錄更新除了屬性的變更。

此資料可透過下列兩個程序還原：

  - 可以還原 RTC 資料庫從原始備份傾印裝置從實際執行環境使用標準的 SQL Server 還原程序，或使用協力廠商的 SQL Server 備份/還原公用程式。

  - 使用當初用來建立實際執行 SQL Server 匯出的 XML 檔案 DBIMPEXP.exe 公用程式可以還原使用者連絡人資料。

此資料還原之後，使用者可以有效地連線至災害復原 Lync Server 2013 集區，及操作像平常一樣。

若要讓使用者能夠連線至災害復原 Lync Server 2013 集區，DNS 記錄變更將會是必要。

實際執行 Lync Server 2013 集區將用戶端使用自動設定資料庫和 DNS SRV 記錄的參照：

  - SRV: \_sip。\_tls。\<網域\>/CNAME: SIP。\<網域\>

  - CNAME: SIP。\<網域\>/cvc-pool-1。\<網域\>

若要加速容錯移轉，您必須更新此 CNAME 記錄，以參照 DROCSPool FQDN:

  - CNAME: SIP。\<網域\>/DROCSPool。\<網域\>

  - Sip。\<網域\>

  - AV.\<網域\>

  - fea-webconf-service。\<網域\>

  - OCSServices。\<網域\>

<div>


> [!IMPORTANT]  
> 如需詳細的系統管理與管理程序，請參閱<A href="lync-server-2013-backing-up-and-restoring-lync-server.md">備份和還原 Lync Server 2013</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中的高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[備份與 Lync Server 2013 中的高可用性 cmdlet](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-csconfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[備份及還原 Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[管理 Lync Server 2013 災害復原、 高可用性及備份服務](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

