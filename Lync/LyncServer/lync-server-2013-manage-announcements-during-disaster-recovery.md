---
title: Lync Server 2013：在災難修復期間管理宣告
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
ms.openlocfilehash: 164c58859a6e92abfbb50b79c12b587c3b65c1a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中管理發生嚴重損壞修復期間的宣告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

Lync Server 2013 支援在中斷期間呼叫未指派號碼的宣告。 在中斷期間還原宣告功能是選用的。 如果您選擇在中斷期間還原宣告，您必須在備份組區中重新建立宣告設定。 本節說明當您選擇在嚴重損壞修復期間還原宣告時，需要執行的動作。

本節適用于使用宣告應用程式的未指派號碼範圍。 本節不適用於使用 Exchange 整合通訊 (UM) 自動語音應答的未指派號碼範圍。

<div>

## <a name="before-an-outage"></a>中斷前

不論您選擇是否要在中斷期間使用宣告，您都應該對您為宣告應用程式所設定的任何自訂音訊檔案採取個別備份。 自訂宣告不會做為 Lync Server 嚴重損壞修復程式的一部分進行備份。 如果您不會對檔案進行個別備份，而且您上傳到伺服器或集區的檔案已損毀、損毀或清除，將會遺失檔案。

如果您沒有自訂音訊檔案的備份副本，而且無法再使用原始的音訊檔案，您可以在先前匯入檔案的伺服器或集區中查看檔案存放區，以找到您為宣告應用程式所設定的音訊檔。 您可以從檔案存放區中複製您為宣告應用程式所設定的所有音訊檔案。

**從檔案存放區複製音訊檔**

1.  在命令列中執行：
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    例如：
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    其中 X-ApplicationServer-X 參照集區之應用程式伺服器的服務 ID (例如，1-ApplicationServer-1 ") 


</div>

<div>

## <a name="during-an-outage"></a>中斷期間

若要在中斷期間使用宣告應用程式，您必須執行本節所述的工作，以在備份組區中重新建立宣告設定。

<div>


> [!NOTE]  
> 我們建議您在容錯移轉至備份組區之後執行這些工作，因為在執行步驟2之後，備份組區便會取得未指派號碼範圍的擁有權。



</div>

<div>


> [!NOTE]  
> 使用 Exchange UM 自動語音應答電話號碼的號碼範圍並非必須執行這些步驟。



</div>

**在備份組區中重新建立宣告設定**

1.  執行下列動作，以重新建立在備份組區的主要集區中部署的宣告：
    
    1.  使用**Import-CsAnnouncementFile** Cmdlet 並指定 Parent 參數的備份組區，將主要集區中使用的任何音訊檔案匯入備份組區。
    
    2.  使用**New-CsAnnouncement** Cmdlet 重新建立每個宣告，並指定 Parent 參數的備份組區。
    
    <div>
    

    > [!NOTE]  
    > 如需使用這些參數在備份組區中建立宣告的詳細資訊，請參閱<A href="lync-server-2013-create-an-announcement.md">create a 宣告 In Lync Server 2013</A>。

    
    </div>

2.  在備份組區中重新建立所有宣告之後，請將使用主要集區中宣告的所有未指派號碼範圍，重新導向至備份組區中重新建立的宣告。
    
    針對使用主要集區中宣告的每個未指派號碼範圍，請執行下列作業：
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>中斷後

當主要集區可用時，您需要將您為中斷而變更的未指派號碼範圍重新導向至主要集區。

<div>


> [!NOTE]  
> 使用 Exchange UM 自動語音應答電話號碼的號碼範圍並非必須執行這些步驟。



</div>

**若要還原主要集區中的宣告**

1.  如果您必須在復原期間重建主要集區，您需要在主要集區中重新建立宣告，方法是匯入音訊檔並建立宣告，就像您為 Parent 參數指定主要集區外。 如需詳細資訊，請參閱本主題前面的「中斷期間」。

2.  針對您為中斷變更而變更的每個未指派號碼範圍，請執行下列作業：
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  （選用）移除您在備份組區中重新建立的宣告。 取得備份組區宣告應用程式的宣告清單。 在命令列中執行：
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    例如：
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    在結果清單中，找出您要移除的宣告並複製 Guid。 針對每個您想要移除的宣告，請執行：
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    例如：
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

