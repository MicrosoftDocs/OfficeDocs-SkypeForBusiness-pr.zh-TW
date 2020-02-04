---
title: Lync Server 2013：啟用或停用已歸檔資料的清除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b06d21cc0154ea57bc028c87c835e4de9a00f1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>啟用或停用 Lync Server 2013 中已歸檔的資料清除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存設定] 來啟用和停用清除及設定清除的執行方式。 這包括下列歸檔設定：

  - 當您部署 Lync Server 2013 時預設會建立的全域配置。

  - 您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。

您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。 如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。

<div>


> [!NOTE]  
> 若要針對駐留在 Lync Server 2013 的使用者使用封存，您必須設定封存原則，以指定是否要針對內部通訊（適用于外部通訊）或兩者啟用封存。 根據預設，不會針對內部或外部通訊啟用封存。 在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。 如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。<BR>如果您在部署存檔後決定要使用 Microsoft Exchange 整合來儲存 Exchange 2013 伺服器上的封存資料和檔案，且您的所有使用者都是位於 Exchange 2013 伺服器上，那麼您應該移除 SQL Server 資料庫配置從您的拓撲。 您必須使用拓撲 Builder 建立器。 如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A>中的封存資料庫選項。



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>若要啟用或停用清除存檔

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

4.  在歸檔設定清單中，按一下適當的全域、網站或池設定的名稱，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：
    
      - 若要啟用清除，請選取 [**允許清除封存資料**] 核取方塊，然後執行下列其中一項操作：
        
          - 若要清除所有記錄，請按一下 [**清除匯出的封存資料]，並儲存已儲存的存檔資料（天數）**，然後指定天數。
        
          - 若只要清除已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。
    
      - 若要停用清除，請清除 [**允許清除封存資料**] 核取方塊。

5.  按一下 [認可]****。

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用歸檔資料清除

啟用及停用自動清除封存資料可以使用 Windows PowerShell 和**CsArchivingConfiguration** Cmdlet 進行管理。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>若要啟用清除所有存檔資料

  - 若要啟用清除所有存檔資料，請將**EnablePurging**屬性設為 true （$True）。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    執行此命令之後，每日 Lync Server 都會清除早于指定的**KeepArchivingDataForDays**屬性值的所有存檔記錄。

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>若要只清除匯出的存檔資料

  - 若要限制清除以封存已匯出到資料檔（使用[Export CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) Cmdlet）的記錄，您也必須將 PurgeExportedArchivesOnly 屬性設為 True （$True）。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    執行此命令之後，Lync Server 將只會清除符合兩個準則的封存記錄：1）它們比指定給**KeepArchivingDataForDays**屬性的值還舊;而且，2）它們已使用**Export CsArchivingData** Cmdlet 進行匯出。

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>若要停用清除所有封存資料

  - 若要停用自動清除封存記錄，請將**EnablePurging**屬性設為 False （$False）。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

如需詳細資訊（包括清除存檔資料的其他選項），請參閱[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[存檔在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)  


[在 Lync Server 2013 中設定及指派存檔原則](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[管理您組織、網站和池的 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

