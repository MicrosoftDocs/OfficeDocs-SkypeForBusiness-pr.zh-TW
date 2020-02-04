---
title: Lync Server 2013：在災害復原期間管理宣告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc987ea579bef4e2b02c8da210efe9a707c5900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>使用 Lync Server 2013 在災害復原期間管理宣告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

Lync Server 2013 支援在中斷期間呼叫未指派號碼的宣告。 在中斷期間還原宣告功能是選用的選項。 如果您選擇在中斷期間還原宣告，您需要在備份池中重新建立您的宣告設定。 本節說明在災害復原期間選擇要還原公告時所需執行的動作。

本節適用于使用宣告應用程式的未指派數量範圍。 本節不適用於使用 Exchange 整合通訊（UM）自動語音應答的未指定數位範圍。

<div>

## <a name="before-an-outage"></a>中斷前

不論您是否選擇要在中斷期間使用宣告，您都應該對您針對宣告應用程式所設定的任何自訂音訊檔案進行個別備份。 在 Lync Server 災害復原程式中，自訂宣告不會進行備份。 如果您不對檔案進行個別備份，且您上傳到伺服器或池中的檔案遭到損毀、損毀或清除，這些檔案將會遺失。

如果您沒有自訂音訊檔案的備份複本，且原始音訊檔案已無法使用，您可以在檔案存放區中尋找您原本要使用的 [伺服器] 或 [池] 所設定的音訊檔案。已匯入檔案。 您可以從檔案存放區中複製您針對宣告應用程式所設定的所有音訊檔案。

**從檔案存放區複製音訊檔案**

1.  在命令列上執行：
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    例如：
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    其中，X-ApplicationServer 是指池之應用程式伺服器的服務識別碼（例如，1-ApplicationServer-1）


</div>

<div>

## <a name="during-an-outage"></a>在中斷期間

若要在中斷期間使用宣告應用程式，您需要執行本節中所述的工作，在備份池中重新建立宣告配置。

<div>


> [!NOTE]  
> 我們建議您在容錯移轉至備份池之後執行這些工作，因為當您執行步驟2之後，備份池就會取得未指派的數位範圍。



</div>

<div>


> [!NOTE]  
> 對於使用 Exchange UM 自動語音應答電話號碼的數位範圍，不需要這些步驟。



</div>

**在備份池中重新建立宣告配置**

1.  請執行下列動作，以重新建立您在備份池中的主要池中部署的公告：
    
    1.  使用**CsAnnouncementFile** Cmdlet 將主要池中使用的任何音訊檔案匯入至備份池，並指定上層參數的備份池。
    
    2.  使用**新的 CsAnnouncement** Cmdlet 來重新建立每個宣告，並指定上層參數的備份池。
    
    <div>
    

    > [!NOTE]  
    > 如需使用這些參數在備份池中建立宣告的詳細資料，請參閱<A href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中建立公告</A>。

    
    </div>

2.  在備份池中重新建立所有宣告之後，請將在主要池中使用宣告的所有未指派數位範圍重定向至 [備份] 池中重新建立的宣告。
    
    針對在主要池中使用宣告的每個未指派編號範圍，請執行下列動作：
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>停機後

當主要池可供使用時，您必須將您針對停機變更的未指派數位範圍重新導向到主要池。

<div>


> [!NOTE]  
> 對於使用 Exchange UM 自動語音應答電話號碼的數位範圍，不需要這些步驟。



</div>

**在主要池中還原宣告**

1.  如果您必須在復原期間重建主要池，您需要在主要池中重新建立宣告，方法是匯入音訊檔案並建立宣告，就像您在備份池中所做的一樣，除非您為父級指定主要池參數. 如需詳細資訊，請參閱本主題前面的「停機期間」。

2.  針對您針對停機時間變更的每個未指派數量範圍，請執行下列動作：
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  或者，移除您在備份池中重新建立的公告。 取得備份池宣告應用程式的宣告清單。 在命令列上執行：
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    例如：
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    在產生的清單中，找出您想要移除並複製 Guid 的宣告。 針對您想要移除的每個宣告，執行：
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    例如：
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

