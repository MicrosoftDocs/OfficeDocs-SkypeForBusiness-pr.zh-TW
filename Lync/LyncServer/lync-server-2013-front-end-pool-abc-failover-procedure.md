---
title: Lync Server 2013：前端集區 ABC 容錯移轉程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf3d12aa519ab7746ccec92998995ed463aa9be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Lync Server 2013 中的前端集區 ABC 容錯移轉程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-22_

使用下列步驟來執行 ABC 容錯移轉程式。 此套裝程式含每個步驟的高層次描述，後面接著要針對每個步驟執行的命令和 Cmdlet。

若要執行 Cmdlet，請使用 [以系統管理員身分執行] 來開啟 Lync Server 管理命令介面。

<div>

## <a name="to-perform-an-abc-failover"></a>執行 ABC 容錯移轉

1.  檢查 [池 A] 是否為 [中央管理伺服器（CMS）] 主機。
    
      - 執行下列 Cmdlet：
        
            Get-CsService -CentralManagement
        
        如果作用中 CMS 的 [身分識別] 欄位指向 [池 A] 的完整功能變數名稱（FQDN），則您可以使用此程式中的步驟2和3，先將中央管理伺服器容錯移轉。 否則，請跳至步驟4。

2.  透過執行下列 Cmdlet，將 CMS 容錯移轉到 [災害復原] 模式中的 [池 B]：
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    在您這樣做之後，建議您將 CMS 從 pool B 移到另一個現有的配對池，以獲得額外的復原能力。 如需詳細資訊，請參閱[移動流覽 CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer).。。

3.  如果 [池 A] 包含 CMS，請將 [池 A] 中的 .LIS 設定匯入到 [池 B] 的 [.LIS] 資料庫（.Lis）中。 只有當您定期備份不在 IIS 中的資料時，才能使用此功能。 若要匯入 .LIS 配置，請執行下列 Cmdlet：
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  將已備份的 Lync Server 回應群組服務工作流程從 [群組 A] 匯入到 [池 B] 中。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>CsRgsConfiguration</STRONG> Cmdlet 目前會要求在 pool A 上的佇列和工作流程名稱與隊 B 上的佇列和工作流程名稱不同。如果名稱不是唯一的，當您執行<STRONG>Import CsRgsConfiguration</STRONG> Cmdlet 時會發生錯誤，且佇列和工作流程需要在 pool B 中重新命名，才能繼續執行匯<STRONG>入-CsRgsConfiguration</STRONG> Cmdlet。

    
    </div>
    
    您有兩個選項可將 [池 A] 的回應群組設定匯入到 pool B。您所使用的選項取決於您是否要覆寫池 B 的應用層級設定，以及 b A 中的應用層級設定。
    
      - 如果您想要覆寫 Pool B 設定，請使用**ReplaceExistingSettings**選項執行**Import CsRgsConfiguration** Cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果您不想覆蓋 Pool B 設定，請使用不含**ReplaceExistingSettings**選項的**Import CsRgsConfiguration** Cmdlet。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 請記住，如果您不想覆寫備份池（池 B）的應用層級設定與主要池（池 A）的設定，當池 A 遺失時，池 A 的應用層級設定將會遺失，因為回應群組應用程式可以針對每個池只儲存一組應用層級設定。 部署 pool C 以取代 pool A 時，必須重新配置應用程式層級設定，包括預設的音樂保留音訊檔案。

    
    </div>

5.  執行下列 Cmdlet 來顯示已匯入的回應群組，以驗證回應群組設定已成功匯入。 請注意，已匯入的回應群組仍由 A pool A 所擁有。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  針對未指定的數位，請將使用「宣告」的未指派數位範圍，移至從池 A 到 pool B 的所選宣告服務。若要執行此動作：
    
      - 重新建立部署在 pool B 上的 [pool A] 中的所有宣告。如果您在 [池 A] 中部署公告時使用任何音訊檔案，則需要這些檔案才能在 pool B 中重新建立公告。若要在 pool B 中重新建立宣告，請使用**CsAnnouncement** Cmdlet，並將 pool b 作為父項服務。
    
      - 已將目標為宣告的所有未指派數位範圍定為在 pool B 中新部署的宣告。針對 a 池 A 的宣告，針對每個未指派的編號範圍執行下列 Cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > 對於使用「Exchange UM」做為選取的宣告服務的未指定編號範圍，不需要此步驟。

    
    </div>

7.  您可以執行下列 Cmdlet，將 [災害復原] （DR）模式中的 [池 A] 容錯移轉到 [池 B]：
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  組建池 C，但不在 pool C 上啟動任何服務。
    
    請注意，您可以使用步驟5和6同時執行此步驟。

9.  執行下列 Cmdlet，強制將駐留在 pool A 的使用者移至 pool C：
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    此時，駐留在 [池 A] 的使用者就會開始遇到服務中斷的問題。 這個中斷會持續至步驟16，在 pool C 上開始進行點服務。

10. 執行下列 Cmdlet，強制將 [池 A] 的會議目錄移至 [pool C]：
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 執行下列 Cmdlet，強迫會議自動語音應答（CAA）連絡人物件從 [池 A] 移至 [pool C]：
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 從 pool B 將會議內容複寫到 pool C。

13. 從 pool B 匯出使用者資料，並執行下列 Cmdlet，將使用者資料匯入到 pool C：
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. 將已備份的通話駐留應用程式資料從 [池 A] 還原到 [pool C]，然後將 [池 A] 的 [通話駐留軌道] 範圍指派給 pool C。
    
      - 您可以透過 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面]，將 [池 A] 的 [通話駐留] 軌道投影範圍重新指派給 pool C。 針對 Lync Server 管理命令介面，請針對指派給 pool A 的每個通話駐留軌道範圍執行下列 Cmdlet （請注意，身分識別參數會參照屬於 pool A 的通話駐留軌道的範圍）：
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - 如果在 [A] （池 A）中針對通話駐留設定了自訂的 [保留的音樂保留]，請在 pool C 中還原通話駐留自訂的音樂封存檔案。
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        例如：
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 最後，使用**CsCpsConfiguration** Cmdlet，在 pool C 上重新配置通話駐留設定。 通話駐留應用程式在每個池中只能儲存一組設定和一個自訂的音樂保留音訊檔案，而且這些設定不會在災難事件中備份或保留。

15. 如果持續聊天的下一個躍點池是指向 [池 A]，請發出併發布拓撲變更，讓下一個躍點伺服器指向 [池 C]。
    
      - 在 [拓撲建立器] 中，將 [永久聊天] 池變更為指向 [池 C] 作為下一個躍點。 若要這樣做，請以滑鼠右鍵按一下 [永久聊天] 池，然後按一下 [**一般**] 索引標籤，然後在 **[下一個躍點] 池中**輸入 [pool C] 的名稱。
    
      - 執行下列 Cmdlet，即可在 pool C 上啟動服務：
        
            Start-csWindowsService
    
    此時，使用者最初駐留在池 A 的服務中斷會結束。

16. 若要匯入到 pool C，請執行下列 Cmdlet，匯出 Lync Server 回應群組服務工作流程（由 pool A 擁有）：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. 從 pool B 將 Lync Server 回應群組服務工作流程匯入到 pool C。
    
    從 pool B 將回應群組設定匯入到 pool C 時，您有兩個選項。您所使用的選項，取決於您是否要覆寫 pool C 的應用層級設定與 pool B 中的應用層級設定。
    
      - 如果您想要覆寫 [Pool C] （設定），請使用**ReplaceExistingSettings**選項執行匯**入 CsRgsConfiguration** Cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果您不想覆蓋 Pool C 設定，請使用不含**ReplaceExistingSettings**選項的**Import CsRgsConfiguration** Cmdlet。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 請記住，如果您不想使用備份池（Pool B）的設定來覆寫 Pool C 的應用層級設定，池 B 的應用層級設定將會遺失，因為回應群組應用程式只能儲存一組應用程式層級每個池的設定。

    
    </div>

18. 執行下列 Cmdlet 以驗證已匯入到 Pool C 的回應群組，以確認回應群組設定已成功匯入。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. 在 pool C 中驗證匯入的設定後，請從 pool B 移除主要池所擁有的回應群組。這將會將回應群組的停機時間降至最低。
    
    此步驟會使用匯出的設定來建立新檔案，然後從 B 文件庫移除檔案。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. 移至 pool C 從 [池 A] 移至 [池 B] 的 [未指定的數位範圍]。
    
      - 在 pool C 中重新建立已從 B 池 B 中的 [池 A] 重新建立的所有宣告。如果您在部署要移動的宣告時使用任何音訊檔案，您將需要使用這些檔案來重新建立在 pool C 中的宣告。若要在 pool C 中重新建立宣告，請使用**CsAnnouncement** Cmdlet （含 pool c）作為父項服務。
    
      - 從 A 池 A 重新置放至池 B 的所有未指派數位範圍，都是從 b 開始。針對需要重新置放的每個未指定編號範圍執行下列 Cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - 可選從 pool B 中移除如果在 pool B 中不再使用，則是在 pool C 中重新建立的宣告。若要移除宣告，請使用**CsAnnouncement** Cmdlet。
        
        <div>
        

        > [!NOTE]  
        > 對於使用「Exchange UM」做為宣告服務的未指定編號範圍，不需要此步驟。

        
        </div>

21. 在 pool B 中，執行下列 Cmdlet，以清除 pool A 的使用者資料：
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. 在拓撲建立器中執行下列動作：
    
      - 取消配對 pool A 和 pool B. 配對池 B 和 pool C。然後從拓撲中移除 [池 A]，然後發佈它。 若要執行此動作：
        
          - 在拓撲建立器中，以滑鼠右鍵按一下 [池 B]，然後按一下 [**編輯屬性**]。
        
          - 按一下左窗格中的 [**復原**]。
        
          - 在 [關聯的**備份] 池**下方的方塊中，選取 [池 C]。請注意，關聯的備份池選取方塊最初會顯示池 A，因為「池 B」先前已與此池建立關聯。
        
          - 選取 [**自動容錯移轉及語音回切**]，然後按一下 **[確定]**。
            
            當您查看此池的詳細資料時，關聯的池現在會出現在右窗格中的 [**復原**] 底下。
        
          - 在主控台樹中，以滑鼠右鍵按一下 [池 A]，然後按一下 [刪除]。
        
          - 發佈拓撲。

23. 在 pool C 上執行引導應用程式，以安裝備份服務應用程式，然後從 pool C 中的本機電腦上的 [部署] 資料夾中執行下列命令，以啟動備份服務應用程式：
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 執行下列 Cmdlet，在 pool B 上重新開機備份服務應用程式：
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. 如果 pool C 是標準版（SE）池，且 pool B 有 CMS，請執行下列 Cmdlet，在 pool C 上手動安裝 CMS 資料庫：
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. 喚醒呼叫 [備份服務]，將舊的會議內容從 pool B 同步處理到在配對 B 和 C 之前產生的 pool C，並將從 pool C 開始的新會議內容同步處理到在啟動池子 C 之後所產生的 pool B，並將 B 和 C 的組合在一起。 若要這樣做，請執行下列 Cmdlet：
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. 針對每個與 [池 A] 相關聯的 Survivable 分支裝置 X：
    
      - 執行下列 Cmdlet 以關閉 SBA X：
        
            Stop-CsWindowsService
    
      - 建立一個檔案，其中包含駐留在 SBA X 上的使用者清單。當使用者移回步驟30中的 SBA X 時，就會需要該清單。 若要這樣做，請執行下列 Cmdlet：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 透過執行下列 Cmdlet，強迫駐留在 SBA X 的使用者移至 pool C：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 首先執行下列 Cmdlet 來更新這些使用者的資料：
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        然後執行此腳本：
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > 系統會針對駐留在 SBAs 的使用者，與 [池 A] 關聯，直到這些使用者移至 [池 C] 為止，才會發生服務中斷。

        
        </div>

28. 在 [拓撲建立器] 中，針對先前與 [池 A] 關聯的每個 SBA X 執行下列動作：
    
      - 變更與 Pool C 的關聯。若要這樣做，請按一下分支網站，展開 [Survivable 分支裝置] 或 [伺服器] 節點，然後按一下 [ **Survivable 分支裝置**]。 然後選取 [**前端] 池、** 這個 Survivable 分支裝置將會連線至 [池 C] 的 [使用者服務] 池，然後按 **[下一步]**。
    
      - 發佈拓撲。 若要這樣做，請在主控台樹中，以滑鼠右鍵按一下新的**Survivable 分支裝置**，按一下 [**拓撲**]，然後按一下 [**發佈**]。

29. 針對現在與 pool C 關聯的每個 SBA X：
    
      - 在 survivable 分支裝置上執行下列 Cmdlet，即可開始 SBA X：
        
            Start-CsWindowsService
    
      - 透過執行下列 Cmdlet，將最初駐留在 SBA X 的使用者從 pool C 移至 SBA X。
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

