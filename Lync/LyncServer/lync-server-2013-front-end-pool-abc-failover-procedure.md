---
title: Lync Server 2013：前端集區 ABC 容錯移轉程式
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
ms.openlocfilehash: aa82180853e8835782d1e39d56fe595e5c7b09b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500800"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Lync Server 2013 中的前端集區 ABC 容錯移轉程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-22_

使用下列步驟來執行 ABC 容錯移轉程式。 此套裝程式含每個步驟的高階描述，以及要針對每個步驟執行的命令和 Cmdlet。

若要執行 Cmdlet，請使用 [以系統管理員身分執行] 開啟 Lync Server 管理命令介面。

<div>

## <a name="to-perform-an-abc-failover"></a>若要執行 ABC 容錯移轉

1.  檢查集區 A 是否為中央管理伺服器的主機 (CMS) 。
    
      - 執行下列 Cmdlet：
        
            Get-CsService -CentralManagement
        
        如果作用中 CMS 的 [身分識別] 欄位指向「集區 A 的 FQDN) 的完整功能變數名稱 (，則您可以使用此程式的步驟2和步驟3，先對中央管理伺服器進行容錯移轉。 否則，請跳至步驟4。

2.  執行下列 Cmdlet，以在嚴重損壞復原模式中將 CMS 容錯移轉至集區 B：
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    執行這項作業之後，建議您將 CMS 從集區 B 移至另一個現有的配對集區，以取得額外的復原能力。 如需詳細資訊，請參閱 [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)。

3.  如果集區 A 包含 CMS，請將 .LIS 設定從集區 A 匯入集區 B 的 .LIS 資料庫 (.Lis) 中。 只有在您已定期備份 .LIS 資料時，才可使用此功能。 若要匯入 .LIS 設定，請執行下列 Cmdlet：
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  將已備份的 Lync Server 回應群組服務工作流程從集區 A 匯入集區 B。
    
    <div>
    

    > [!NOTE]  
    > 目前， <STRONG>Import-CsRgsConfiguration</STRONG> Cmdlet 要求集區 a 上的佇列和工作流程名稱與集區 B 上的佇列和工作流程名稱不同。如果名稱不具差異，當您執行 <STRONG>Import-CsRgsConfiguration</STRONG> Cmdlet 時，將會發生錯誤，而且在繼續進行 <STRONG>Import-CsRgsConfiguration</STRONG> Cmdlet 之前，必須先在集區 B 中重新命名佇列和工作流程。

    
    </div>
    
    您有兩個選項可將「集區 A」的回應群組設定匯入至集區 B。使用哪個選項取決於您是否要覆寫集區 B 的應用層級設定與集區 A 中的應用層級設定。
    
      - 如果您想要覆寫集區 B 設定，請使用**ReplaceExistingSettings**選項來執行**Import-CsRgsConfiguration** Cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果您不想要覆寫集區 B 設定，請使用不含**ReplaceExistingSettings**選項的**Import-CsRgsConfiguration** Cmdlet。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 請注意，如果您不想要使用主要集區的設定覆寫備份組區的應用層級設定 (集區 B)  (集區 A) ，集區 A 的應用層級設定會在遺失集區 A 時遺失，因為回應群組應用程式只能在每個集區中儲存一組應用層級設定。 當部署集區 C 以取代集區 A 時，必須重新設定應用層級設定，包括預設的等候音樂音訊檔。

    
    </div>

5.  執行下列 Cmdlet 以顯示匯入的回應群組，確認回應群組設定匯入成功。 請注意，匯入的回應群組仍然歸集區 A 所有。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  若未指派號碼，請將使用「宣告」的未指派號碼範圍，移至集區 A 至集區 B 的選取宣告服務。若要執行此動作：
    
      - 重新建立部署于集區 B 上集區 A 中的所有宣告。如果在集區 A 中部署宣告時使用任何音訊檔案，則需要這些檔案，以在集區 B 中重新建立宣告。若要在集區 B 中重新建立宣告，請使用 **New-CsAnnouncement** Cmdlet，搭配集區 b 做為上級服務。
    
      - 將所有以集區 A 宣告為宣告的未指派號碼範圍，都重新導向至集區 B 中新近部署的宣告。針對針對集區 A 宣告的每個未指派號碼範圍，執行下列 Cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > 若未指派的號碼範圍使用「Exchange UM」做為選取的宣告服務，則不需要此步驟。

    
    </div>

7.  執行下列 Cmdlet，將嚴重損壞修復 (DR) 模式中的集區 A 容錯移轉至集區 B：
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  組建集區 C，但不啟動集區 C 上的任何服務。
    
    請注意，您可以使用步驟5和6同時執行此步驟。

9.  執行下列 Cmdlet，強制將駐留在集區 A 上的使用者移至集區 C：
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    此時，位於集區 A 的使用者將開始經歷服務中斷。 這種中斷會繼續進行，直到第16步，在集區 C 上啟動了點服務。

10. 執行下列 Cmdlet，強制集區 A 的會議目錄移至集區 C：
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 執行下列 Cmdlet，強制會議自動語音應答 (CAA) Contact 物件從集區 A 移至集區 C：
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 將會議內容從集區 B 複製到集區 C。

13. 從集區 B 匯出使用者資料，並執行下列 Cmdlet，將使用者資料匯入集區 C：
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. 將從集區 A 備份的通話駐留應用程式資料還原到集區 C，並將集區 A 的通話駐留軌道範圍指派給集區 C。
    
      - 您可以透過 Lync Server 控制台或 Lync Server 管理命令介面，將集區 A 的通話駐留軌道範圍重新指派至集區 C。 針對 Lync Server 管理命令介面，針對指派給集區 A (的每個通話駐留軌道範圍執行下列 Cmdlet。請注意，Identity 參數是指屬於集區 A) 的通話駐留軌道範圍：
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - 如果已針對集區 A 中的通話駐留設定自訂的已等候音樂，請在集區 C 中還原通話駐留自訂的封存暫停檔案。
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        例如：
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 最後，使用 **Set-CsCpsConfiguration** Cmdlet 重新設定集區 C 上的通話駐留設定。 通話駐留應用程式只能為每個集區儲存一組設定及一個自訂的音樂暫止音訊檔，而且在發生嚴重損壞時，不會備份或保留這些設定。

15. 如果持續性聊天的下一個躍點集區指向集區 A，請建立併發行拓撲變更，使下一個躍點伺服器指向集區 C。
    
      - 在 [拓撲產生器] 中，將 Persistent Chat 集區變更為指向 [集區 C] 做為下一個躍點。 若要這麼做，請在 Persistent Chat 集區上按一下滑鼠右鍵，然後按一下 [ **一般** ] 索引標籤，然後在 **[下一個躍點集區]** 中輸入集區 C 的名稱。
    
      - 執行下列 Cmdlet，以在集區 C 上啟動服務：
        
            Start-csWindowsService
    
    此時，使用者最初位於集區 A 上的服務中斷會結束。

16. 執行下列 Cmdlet，從集區 A 所擁有的集區 B 匯出 Lync Server 回應群組服務工作流程，以匯入集區 C：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. 將 Lync Server 回應群組服務工作流程匯入集區 B 的集區 C。
    
    您有兩個選項可將回應群組設定從集區 B 匯入集區 C。使用哪個選項取決於您是否要使用集區 B 中的應用層級設定來覆寫集區 C 的應用層級設定。
    
      - 如果您想要覆寫集區 C 設定，請使用**ReplaceExistingSettings**選項執行**Import-CsRgsConfiguration** Cmdlet：
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 如果您不想要覆寫集區 C 設定，請使用不含**ReplaceExistingSettings**選項的**Import-CsRgsConfiguration** Cmdlet。
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 請注意，如果您不想要使用備份組區的設定覆寫集區 C 的應用層級設定 (集區 B) ，集區 B 的應用層級設定會遺失，因為回應群組應用程式只能為每個集區儲存一組應用層級設定。

    
    </div>

18. 執行下列 Cmdlet 以顯示已匯入至集區 C 的回應群組，確認回應群組設定匯入成功。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. 在集區 C 中驗證匯入的設定之後，移除集區 B 的主要集區所擁有的回應群組。這會將回應群組的停機時間降至最低。
    
    此步驟會使用匯出的設定來建立新檔案，然後從集區 B 中移除檔案。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. 移至集區 C 從集區 A 移至集區 B 的未指派號碼範圍。
    
      - 在集區 C 中重新建立從集區 B 的集區 A 重新建立的所有宣告。如果在部署要移動的宣告時使用任何音訊檔案，您必須使用這些檔案，以在集區 C 中重新建立宣告。若要在集區 C 中重新建立宣告，請使用 **New-CsAnnouncement** Cmdlet 搭配集區 c 做為上級服務。
    
      - 重新定向至集區 C 從集區 A 重新置放至集區 B 的所有未指派號碼範圍。請針對需要重新置放的每個未指派號碼範圍，執行下列 Cmdlet：
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      -  (選用) 從集區 B 中移除如果已不再在集區 B 中使用，則會在集區 C 中重新建立的宣告。若要移除宣告，請使用 **remove-CsAnnouncement** Cmdlet。
        
        <div>
        

        > [!NOTE]  
        > 對於使用「Exchange UM」做為宣告服務的未指派號碼範圍，不需要此步驟。

        
        </div>

21. 執行下列 Cmdlet，清除集區 B 中集區 B 的使用者資料：
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. 請在拓撲產生器中執行下列動作：
    
      - Unpair 集區 A 及集區 B。對集區 B 和集區 C。然後從拓撲移除集區 A，然後發佈它。 若要這麼做︰
        
          - 在 [拓撲產生器] 中，以滑鼠右鍵按一下 [集區 B]，然後按一下 [ **編輯屬性**]。
        
          - 按一下左窗格中的 [ **復原** ]。
        
          - 在 [ **關聯備份組**區] 下方的方塊中，選取 [集區 C]。請注意，關聯的備份組區選擇方塊最初會顯示集區 A，因為集區 B 先前與此集區相關聯。
        
          - 選取 [語音自動容錯移轉和容錯回復]****，然後按一下 [確定]****。
            
            現在當您檢視此集區的詳細資料時，會在右窗格的 [恢復]**** 中顯示關聯的集區。
        
          - 在主控台樹中，以滑鼠右鍵按一下 [集區 A]，然後按一下 [刪除]。
        
          - 發行拓撲。

23. 在集區 C 上執行啟動應用程式以安裝備份服務應用程式，然後從集區 C 中本機電腦上的部署資料夾中執行下列動作，以啟動備份服務應用程式：
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 執行下列 Cmdlet，以重新開機集區 B 上的備份服務應用程式：
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. 如果集區 C 是 Standard Edition (SE) 集區和集區 B 有 CMS，請執行下列 Cmdlet 手動在集區 C 上安裝 CMS 資料庫：
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. 呼叫備份服務，從集區 B 同步處理舊的會議內容，並將該內容從集區 B 同步處理至 a 集區 c 之前所產生的集區 C，並同步處理從集區 C 開始，並將 B 和 C 成對在一起時產生的集區 B 的新會議內容。 若要這麼做，請執行下列 Cmdlet：
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. 針對與集區 A 相關聯的每個 Survivable 分支裝置 X：
    
      - 執行下列 Cmdlet 以關閉 SBA X：
        
            Stop-CsWindowsService
    
      - 建立包含位於 SBA X 上的使用者清單的檔案。當使用者移回步驟30中的 SBA X 時，就會需要該清單。 若要這麼做，請執行下列 Cmdlet：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 執行下列 Cmdlet，強制將位於 SBA X 的使用者移至集區 C：
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 先執行下列 Cmdlet，更新這些使用者的資料：
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        然後執行下列腳本：
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > 在將使用者移至集區 C 之前，會針對位於 Sba 且與集區 A 關聯的使用者執行服務中斷。

        
        </div>

28. 在 [拓撲產生器] 中，針對先前與集區 A 相關聯的每個 SBA X 執行下列作業：
    
      - 變更與集區 C 的關聯。若要這麼做，請按一下分支網站，展開 [Survivable 分支裝置] 或 [伺服器] 節點，然後按一下 [ **Survivable Branch 裝置**]。 然後選取前端集區，此 Survivable Branch 裝置將會連線至集區 C 的 **使用者服務集** 區，然後按 **[下一步]**。
    
      - 發行拓撲。 若要執行此動作，請在主控台樹中，以滑鼠右鍵按一下新的 **Survivable Branch 裝置**，按一下 [ **拓撲**]，然後按一下 [ **發佈**]。

29. 對於現在與集區 C 相關聯的每個 SBA X：
    
      - 在 survivable branch 裝置上執行下列 Cmdlet，以啟動 SBA X：
        
            Start-CsWindowsService
    
      - 執行下列 Cmdlet，將原來位於 SBA X 的使用者，從集區 C 移至 SBA X。
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

