---
title: Lync Server 2013：在災難修復期間管理宣告
description: Lync Server 2013：在發生嚴重損壞修復時管理宣告。
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
ms.openlocfilehash: d85dfcd15c9c3650bafafa6fa7702e19ac9c4f7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550629"
---
# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="e37b0-103">在 Lync Server 2013 中管理發生嚴重損壞修復期間的宣告</span><span class="sxs-lookup"><span data-stu-id="e37b0-103">Manage announcements during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e37b0-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e37b0-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e37b0-105">Lync Server 2013 支援在中斷期間呼叫未指派號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="e37b0-105">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="e37b0-106">在中斷期間還原宣告功能是選用的。</span><span class="sxs-lookup"><span data-stu-id="e37b0-106">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="e37b0-107">如果您選擇在中斷期間還原宣告，您必須在備份組區中重新建立宣告設定。</span><span class="sxs-lookup"><span data-stu-id="e37b0-107">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="e37b0-108">本節說明當您選擇在嚴重損壞修復期間還原宣告時，需要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="e37b0-108">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="e37b0-109">本節適用于使用宣告應用程式的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="e37b0-109">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="e37b0-110">本節不適用於使用 Exchange 整合通訊 (UM) 自動語音應答的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="e37b0-110">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="e37b0-111">中斷前</span><span class="sxs-lookup"><span data-stu-id="e37b0-111">Before an Outage</span></span>

<span data-ttu-id="e37b0-112">不論您選擇是否要在中斷期間使用宣告，您都應該對您為宣告應用程式所設定的任何自訂音訊檔案採取個別備份。</span><span class="sxs-lookup"><span data-stu-id="e37b0-112">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="e37b0-113">自訂宣告不會做為 Lync Server 嚴重損壞修復程式的一部分進行備份。</span><span class="sxs-lookup"><span data-stu-id="e37b0-113">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="e37b0-114">如果您不會對檔案進行個別備份，而且您上傳到伺服器或集區的檔案已損毀、損毀或清除，將會遺失檔案。</span><span class="sxs-lookup"><span data-stu-id="e37b0-114">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="e37b0-115">如果您沒有自訂音訊檔案的備份副本，而且無法再使用原始的音訊檔案，您可以在先前匯入檔案的伺服器或集區中查看檔案存放區，以找到您為宣告應用程式所設定的音訊檔。</span><span class="sxs-lookup"><span data-stu-id="e37b0-115">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="e37b0-116">您可以從檔案存放區中複製您為宣告應用程式所設定的所有音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="e37b0-116">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="e37b0-117">**從檔案存放區複製音訊檔**</span><span class="sxs-lookup"><span data-stu-id="e37b0-117">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="e37b0-118">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="e37b0-118">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="e37b0-119">例如：</span><span class="sxs-lookup"><span data-stu-id="e37b0-119">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="e37b0-120">其中 X-ApplicationServer-X 參照集區之應用程式伺服器的服務 ID (例如，1-ApplicationServer-1 ") </span><span class="sxs-lookup"><span data-stu-id="e37b0-120">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="e37b0-121">中斷期間</span><span class="sxs-lookup"><span data-stu-id="e37b0-121">During an Outage</span></span>

<span data-ttu-id="e37b0-122">若要在中斷期間使用宣告應用程式，您必須執行本節所述的工作，以在備份組區中重新建立宣告設定。</span><span class="sxs-lookup"><span data-stu-id="e37b0-122">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e37b0-123">我們建議您在容錯移轉至備份組區之後執行這些工作，因為在執行步驟2之後，備份組區便會取得未指派號碼範圍的擁有權。</span><span class="sxs-lookup"><span data-stu-id="e37b0-123">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e37b0-124">使用 Exchange UM 自動語音應答電話號碼的號碼範圍並非必須執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="e37b0-124">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="e37b0-125">**在備份組區中重新建立宣告設定**</span><span class="sxs-lookup"><span data-stu-id="e37b0-125">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="e37b0-126">執行下列動作，以重新建立在備份組區的主要集區中部署的宣告：</span><span class="sxs-lookup"><span data-stu-id="e37b0-126">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="e37b0-127">使用 **Import-CsAnnouncementFile** Cmdlet 並指定 Parent 參數的備份組區，將主要集區中使用的任何音訊檔案匯入備份組區。</span><span class="sxs-lookup"><span data-stu-id="e37b0-127">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="e37b0-128">使用 **New-CsAnnouncement** Cmdlet 重新建立每個宣告，並指定 Parent 參數的備份組區。</span><span class="sxs-lookup"><span data-stu-id="e37b0-128">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e37b0-129">如需使用這些參數在備份組區中建立宣告的詳細資訊，請參閱 <A href="lync-server-2013-create-an-announcement.md">create a 宣告 In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="e37b0-129">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="e37b0-130">在備份組區中重新建立所有宣告之後，請將使用主要集區中宣告的所有未指派號碼範圍，重新導向至備份組區中重新建立的宣告。</span><span class="sxs-lookup"><span data-stu-id="e37b0-130">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="e37b0-131">針對使用主要集區中宣告的每個未指派號碼範圍，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e37b0-131">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="e37b0-132">中斷後</span><span class="sxs-lookup"><span data-stu-id="e37b0-132">After the Outage</span></span>

<span data-ttu-id="e37b0-133">當主要集區可用時，您需要將您為中斷而變更的未指派號碼範圍重新導向至主要集區。</span><span class="sxs-lookup"><span data-stu-id="e37b0-133">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e37b0-134">使用 Exchange UM 自動語音應答電話號碼的號碼範圍並非必須執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="e37b0-134">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="e37b0-135">**若要還原主要集區中的宣告**</span><span class="sxs-lookup"><span data-stu-id="e37b0-135">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="e37b0-136">如果您必須在復原期間重建主要集區，您需要在主要集區中重新建立宣告，方法是匯入音訊檔並建立宣告，就像您為 Parent 參數指定主要集區外。</span><span class="sxs-lookup"><span data-stu-id="e37b0-136">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter.</span></span> <span data-ttu-id="e37b0-137">如需詳細資訊，請參閱本主題前面的「中斷期間」。</span><span class="sxs-lookup"><span data-stu-id="e37b0-137">For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="e37b0-138">針對您為中斷變更而變更的每個未指派號碼範圍，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e37b0-138">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="e37b0-139">（選用）移除您在備份組區中重新建立的宣告。</span><span class="sxs-lookup"><span data-stu-id="e37b0-139">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="e37b0-140">取得備份組區宣告應用程式的宣告清單。</span><span class="sxs-lookup"><span data-stu-id="e37b0-140">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="e37b0-141">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="e37b0-141">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="e37b0-142">例如：</span><span class="sxs-lookup"><span data-stu-id="e37b0-142">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="e37b0-143">在結果清單中，找出您要移除的宣告並複製 Guid。</span><span class="sxs-lookup"><span data-stu-id="e37b0-143">In the resulting list, locate the announcements you want to remove and copy the GUIDs.</span></span> <span data-ttu-id="e37b0-144">針對每個您想要移除的宣告，請執行：</span><span class="sxs-lookup"><span data-stu-id="e37b0-144">For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="e37b0-145">例如：</span><span class="sxs-lookup"><span data-stu-id="e37b0-145">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

