---
title: Lync Server 2013：災害復原測試
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
ms.openlocfilehash: f7c6c3b7c3b5d78324fe9c674650dd94338baea4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013 中的災害復原測試

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-26_

針對 Lync Server 2013 pool server 執行系統復原，以測試您已記錄的災害復原程式。 本測試將會模擬一台伺服器的完整硬體故障狀況，並將協助保證各項資源、計畫和資料都可復原。 請嘗試每月變換測試重點，以便您組織每次都能測試不同伺服器的故障狀況或設備的其他部件。

請注意，組織執行災害復原測試的排程各不相同，切勿忽略或疏於進行災害復原測試。

<div>


將您的 Lync Server 2013 拓撲、原則和配置設定匯出至檔案。 除此之外，在升級、發生硬體故障或某些其他問題而造成資料遺失之後，此檔案還可在用於將此資訊還原至中央管理存放區。

將您的 Lync Server 2013 拓撲、原則和設定設定匯入中央管理儲存體或本機電腦，如下列命令所示：

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

若要備份 Lync Server 2013 的資料：

  - 使用標準的 SQL Server 備份程式將資料庫轉儲至檔案或磁帶轉儲裝置，以備份 RTC 及 LCSLog 資料庫。

  - 使用協力廠商備份應用程式，將資料備份至檔案或磁帶。

  - 使用 Export-CsUserData cmdlet 來建立整個 RTC 資料庫的 XML 匯出。

  - 使用檔案系統備份或協力廠商來備份會議內容和規範記錄。

  - 使用 Export CsConfiguration 命令列工具來備份 Lync Server 2013 設定。

容錯移轉程序的第一步驟包含將使用者從生產集區強制移至災害復原集區。

此一步驟將為強制移動，因為生產集區將無法接受使用者遷移。

除了 RTC SQL 資料庫上的記錄更新之外，Lync Server 2013 移動使用者程式也會對使用者帳戶物件上的屬性有實際的變更。

這項資料可透過下列兩項程序還原：

  - 您可以使用標準的 SQL Server 還原程式，或使用協力廠商的備份/還原公用程式，從生產 SQL Server 上的原始備份轉儲裝置還原 RTC 資料庫。

  - 使用從生產 SQL Server 匯出建立的 XML 檔案便可透過 DBIMPEXP.exe 公用程式還原使用者聯絡資料。

還原此資料之後，使用者就能有效地連線至災害復原 Lync Server 2013 池，並照常運作。

若要讓使用者能夠連線到災害復原 Lync Server 2013 池，必須變更 DNS 記錄。

用戶端將會使用自動設定和 DNS SRV 記錄來參照生產 Lync Server 2013 池：

  - SRV： \_sip。\_tls。\<網域\> /CNAME： SIP。\<網域\>

  - CNAME： SIP。\<網域\> /cvc-pool-1。\<網域\>

若要輔助容錯移轉，必須更新這項 CNAME 記錄才能參考 DROCSPool FQDN：

  - CNAME： SIP。\<網域\> /DROCSPool。\<網域\>

  - 呼吸.\<網域\>

  - AV.\<網域\>

  - webconf.\<網域\>

  - OCSServices.\<網域\>

<div>


> [!IMPORTANT]  
> 如需詳細的管理與管理程式，請參閱<A href="lync-server-2013-backing-up-and-restoring-lync-server.md">備份和還原 Lync Server 2013</A>。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Lync Server 2013 中的備份和高可用性 Cmdlet](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[匯入-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[備份和還原 Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[管理 Lync Server 2013 災害復原、高可用性及備份服務](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

