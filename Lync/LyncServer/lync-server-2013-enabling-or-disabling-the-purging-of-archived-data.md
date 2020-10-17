---
title: Lync Server 2013：啟用或停用封存資料的清除
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
ms.openlocfilehash: 308ba7b91fbe776ed49d72c54e2986ad95d080fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500940"
---
# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>啟用或停用 Lync Server 2013 中的封存資料清除功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在 [Lync Server 2013 控制台] 中，您可以使用封存設定來啟用及停用清除及設定清除的執行方式。 這包含下列封存組態：

  - 當您部署 Lync Server 2013 時，預設會建立全域設定。

  - 選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。

您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。 如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]  
> 若要將封存用於位於 Lync Server 2013 的使用者，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或兩者的封存。 預設並沒有啟用內部或外部通訊的封存。 以任何原則啟用封存之前，您應先為部署指定適用的封存組態，然後如上一節中所述，選用地針對網站與集區指定封存組態。 如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。<BR>如果您在部署封存後決定要使用 Microsoft Exchange 整合將封存資料和檔案儲存在 Exchange 2013 伺服器上，而且所有使用者都位於 Exchange 2013 伺服器上，則應該從拓撲中移除 SQL Server 資料庫設定。 您必須使用拓撲產生器來執行這項作業。 如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A> 中的封存資料庫選項。



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>啟用或停用封存的清除功能

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中 **，按一下 [****監視與**封存]，然後按一下 [封存設定]。

4.  按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯]**** 和 [顯示詳細資料]****，然後執行下列作業：
    
      - 若要啟用清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項：
        
          - 若要清除所有記錄，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。
        
          - 若只要清除已匯出的資料，請按一下 **[只清除匯出的封存資料]**。
    
      - 若要停用清除，請清除 **[啟用封存資料的清除]** 核取方塊。

5.  按一下 **[認可]**。

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用封存資料的清除

啟用和停用封存資料的自動清除可使用 Windows PowerShell 和 **get-csarchivingconfiguration** Cmdlet 來管理。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>啟用所有封存資料的清除

  - 若要啟用所有封存資料的清除，請將 **EnablePurging** 屬性設為 true ($True)。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    在執行這個命令之後，Lync Server 會清除所有比指定的 **KeepArchivingDataForDays** 屬性值還舊的封存記錄。

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>僅啟用匯出的封存資料的清除

  - 若要使用 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) Cmdlet 來限制清除已匯出至資料檔案 (的封存記錄，) 您也必須將 PurgeExportedArchivesOnly 屬性設定為 True ($True) 。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    在執行這個命令之後，Lync Server 只會清除符合兩個準則的封存記錄： 1) 這些記錄會舊于 **KeepArchivingDataForDays** 屬性指定的值。而且，2) 使用 **Export-CsArchivingData** Cmdlet 匯出。

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>停用所有封存資料的清除

  - 若要停用封存記錄的自動清除，請將 **EnablePurging** 屬性設為 False ($False)。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

如需詳細資訊，包括清除封存資料的其他選項，請參閱 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) 指令程式的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的封存運作方式](lync-server-2013-how-archiving-works.md)  


[在 Lync Server 2013 中設定和指派封存原則](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

