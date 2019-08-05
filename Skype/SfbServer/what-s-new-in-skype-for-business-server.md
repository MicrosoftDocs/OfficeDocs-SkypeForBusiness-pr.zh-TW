---
title: 商務用 Skype Server 2015 的新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: '摘要: 請閱讀本主題以瞭解商務用 Skype Server 2015 中的新功能。 如需新用戶端體驗的詳細資訊, 請參閱 Lync 現在已開始商務用 Skype--查看新功能。'
ms.openlocfilehash: e59d158242a5d2dd4b129da3a531749b22e3eadc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191980"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的新功能

**摘要:** 若要瞭解商務用 Skype Server 2015 中的新功能, 請閱讀本主題。 如需新用戶端體驗的詳細資訊, 請參閱[Lync 現在已開始商務用 Skype--查看新功能](https://go.microsoft.com/fwlink/p/?LinkId=529022)。
  
Lync 現在是商務用 Skype, 這是一種通訊與共同作業平臺, 透過 Skype 使用企業級安全性、合規性及控制 Lync 來提供更具創意的體驗。 商務用 Skype 提供功能, 包括目前狀態、IM、語音和視頻通話, 以及線上會議。 商務用 Skype 提供新的用戶端體驗、新的伺服器版本, 以及 Office 365 中服務的更新。 如果貴組織中的使用者已經熟悉 Skype, 他們將會欣賞商務用 Skype 的強大功能與簡潔性, 輕鬆找到並與同事進行連接。 如果貴組織中的使用者是從 Lync 傳送到商務用 Skype, 他們就會辨識他們已使用的所有功能, 但在全新的介面中, 有簡化的控制項和新的新增功能。 除了新的用戶端體驗之外, 商務用 Skype Server 2015 提供數種新功能來改善內部部署伺服器與混合式解決方案的可管理性。
  
商務用 Skype Server 2015 中的新功能包括:
  
- 使用者體驗  
- 語音及視頻支援
- 行動支援
- 內部部署伺服器的管理
- 部署和管理混合式解決方案
- 多重要素驗證支援
    
## <a name="user-experience"></a>使用者體驗

商務用 Skype 用戶端看起來與消費者版本的 Skype 非常相似, 且使用相同的按鈕和圖示。 較少的功能表和更簡單的任務階層圖, 讓使用者可以輕鬆地快速找到所需的控制項和命令。 
  
商務用 Skype 包括上述所述的新使用者經驗, 以及先前發行的 Lync 2013 使用者體驗。 包括這兩種體驗可讓企業透過控制新用戶端推出的程式和時間來管理其使用者的變更。預設的使用者體驗取決於您所使用的伺服器版本。 系統管理員可以使用**CsClientPolicy** Cmdlet 與 EnableSkypeUI 參數, 選擇慣用的體驗。 如需有關設定用戶端體驗的詳細資訊, 請參閱使用商務用 skype 的商務用 Skype 和[桌面用戶端功能比較](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)來[設定用戶端體驗](deploy/deploy-clients/configure-the-client-experience.md)。
  
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。 在您嘗試將用戶端環境設定為使用 Lync 2013 用戶端之前, 請先檢查用戶端版本, 以確保它不是以數位16開頭;例如: x.x.x。 
  
## <a name="voice-and-video-improvements"></a>語音及影片改良功能

商務用 Skype Server 2015 包含語音及視頻功能的改良功能, 包括呼叫資料收集和分析, 以及改良與協力廠商視頻 teleconferencing 系統之間的互通性。
  
### <a name="call-data-collection-and-analysis"></a>呼叫資料收集和分析

[通話頻率] 功能可讓商務用 Skype Server 2015 系統管理員收集通話資料。 此功能僅適用于內部部署部署。 在完成通話之後, 系統會提示使用者進行問卷調查。 如需詳細資訊, 請參閱[在商務用 Skype Server 2015 中評級我的通話](manage/health-and-monitoring/rate-my-call.md)。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>改良與協力廠商影片 teleconferencing 系統的互通性

影片交互操作伺服器 (VIS) 充當商務用 Skype Server 與 Cisco Video teleconferencing (VTC) 系統之間的媒介。 加入會議時, 使用者現在可以選取 Cisco VTC 系統。 影片交互操作伺服器 (VIS) 是以獨立伺服器角色的形式實現, 以進行內部部署。 如需詳細資訊, 請參閱[商務用 Skype server 2015 中的視頻互通性伺服器規劃](plan-your-deployment/video-interop-server.md)。
  
### <a name="call-via-work"></a>透過公司通話

[透過工作通話] 功能可讓企業使用者撥打商務用 Skype 用戶端的語音通話。 當使用者撥打電話時, 會將它從商務用 Skype 路由到始發者的 PBX 或 PSTN 手機。 發信方接聽電話後, 通話就會導向目的地號碼。 呼叫收件者的答案, 且通話是使用商務用 Skype 服務做為 [控制台] 來建立。 始發者可以從商務用 Skype 管理其目前狀態和通話控制。 伺服器管理員可透過企業的工作來啟用及設定通話。 如需詳細資訊, 請參閱[在商務用 Skype Server 2015 中使用工作規劃通話](plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 
  
## <a name="mobile-device-support-improvements"></a>行動裝置支援的改良功能

改善行動裝置支援的功能包括改善企業版使用者的行動裝置體驗 (例如存取交談記錄及記錄資料、增強行動會議體驗, 以及跨 Office 的單一登入支援)。 此外, 還改良了 Android 支援、效能改善以及功能, 以簡化透過通用 App 架構的整合。 
  
> [!NOTE]
> Lync 2013 UCWA 伺服器必須升級至商務用 Skype Server 2015, 才能支援行動用戶端。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>現在可在行動裝置上使用伺服器端交談記錄

若要讓行動裝置存取交談記錄、未接的 IM, 以及通話記錄資料, 現在可透過伺服器針對所有行動用戶端處理此資訊的封存。 IM 的自動接受功能可在行動使用者沒有立即回應 IM 時, 避免伺服器超時訊息, 改善可靠性。 若要利用以伺服器為基礎的 Exchange/Outlook 資料夾整合、Exchange Server 2013 或更新版本, 以及更新的行動用戶端, 都是必要的。 
  
### <a name="enhanced-meeting-experiences"></a>增強的會議體驗

在桌面上提供的會議功能現在也可供行動使用者使用。 新功能包括:
  
- 共用 PowerPoint 內容的非同步導覽
- 簡報者取得共用 PowerPoint 內容的能力
- 簡報者的大廳管理, 允許他們承認或拒絕參與者
    
### <a name="skype-for-business-on-android-improvements"></a>Android 版商務用 Skype 改良功能

Android 版商務用 skype 現已提供與 iOS 版商務用 Skype 和 Windows 版商務用 Skype 中可用的功能:
  
- 繼續或重新加入交談
- 啟用憑證和被動驗證
- 邀請其他人加入交談
- 輕鬆開始群組交談
- 在不是商務用 Skype 使用者的情況下加入會議
- 在 Android 平板電腦上啟用智慧型電話 UI
- 新增或移除參與者以管理會議
    
> [!NOTE]
> 這些功能需要 Android OS 版本4.0 或更新版本。 
  
## <a name="management-of-on-premises-servers"></a>內部部署伺服器的管理

商務用 Skype Server 2015 提供數種新功能來改善內部部署伺服器的可管理性, 包括就地升級、智慧設定、改良的修補程式和升級程式、改良的前端池冷啟動功能、SQL Server AlwaysOn支援, 以及集中式記錄及疑難排解。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>內部部署伺服器的就地升級

您現在可以使用新的就地升級功能將 Lync Server 2013 系統升級到商務用 Skype Server 2015 2013, 從而減少部署商務用 Skype Server 2015 的整體成本。
  
就地升級有兩種情況: 移動使用者方法 (不需要停機) 和離線方法 (需要停機時間)。 如需適合您企業的升級程式的詳細資訊, 請參閱[規劃升級到商務用 Skype Server 2015](plan-your-deployment/upgrade.md)。 
  
> [!NOTE]
> 如果您是從 Lync Server 2010 升級, 就無法使用就地選項。 如需從 Lync Server 2010 升級的詳細資訊, 請參閱[規劃升級到商務用 Skype server 2015](plan-your-deployment/upgrade.md)。 
  
### <a name="smart-setup"></a>智慧設定

[智慧設定] 功能 (自動偵測及下載更新) 現已成為安裝程式的一部分。 在安裝期間, 系統會詢問使用者安裝程式是否應該檢查更新。 如需詳細資訊, 請參閱[安裝商務用 Skype Server 2015](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>改良的前端伺服器修補程式和升級程式

商務用 Skype 伺服器引進了兩個新的 Cmdlet, 可協助升級或修補前端伺服器, 比在舊版 Lync Server 中更容易。
  
如果您需要套用修補程式, 或執行任何其他維護作業至前端伺服器, 只要輸入**Invoke CsComputerFailOver** , 然後指定該伺服器的名稱即可。 商務用 Skype 伺服器會將該伺服器的工作負荷暫時移至池中的其他伺服器。 接著, 您可以執行維護作業, 然後使用**CsComputerFailback** Cmdlet 將該伺服器移回服務中。 如果您需要修補池中的每個伺服器, 只要針對每個伺服器逐一執行此程式 (一次一個)。 這些新的 Cmdlet 能讓您以更快的速度與舊版進行修補, 以及更可靠且更簡單的工作流程。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>改良的前端池冷啟動功能

商務用 Skype Server 引進了新的 Cmdlet, 可簡化並改善冷啟動整個前端池的程式。 當您使用新的**CsPool** Cmdlet 時, 它會檢查池中所有前端伺服器的必備元件, 然後嘗試啟動每個伺服器。 如果它遇到任何問題, 就會進行診斷並提醒您詳細資料和因應措施。 在某些情況下, 即使有些個別伺服器無法啟動, 也能讓您啟動池。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>針對內部部署伺服器的 SQL Server AlwaysOn 支援

商務用 Skype Server 2015 新增對 SQL Server AlwaysOn 可用性群組和 SQL Server AlwaysOn 容錯移轉叢集實例的支援。 除了這些功能之外, 商務用 Skype 伺服器仍會繼續支援資料庫鏡像與 SQL Server 群集, 就像在過去版本的 Lync Server 中一樣。
  
SQL Server AlwaysOn 可用性群組是 SQL Server 2012 與 SQL Server 2014 中的高可用性和災害復原方案, 可提供資料庫鏡像的替代方案。 可用性群組支援一組相互失敗的分散式資料庫 (稱為可用性資料庫) 的容錯移轉環境。 可用性群組支援一組可讀寫的主資料庫, 以及一到四組對應的次要資料庫。 您也可以選擇將次要資料庫提供給唯讀存取, 以及進行一些備份作業。
  
SQL Server 容錯移轉叢集實例利用 Windows Server 容錯移轉叢集 (WSFC) 功能, 透過伺服器實例層級的冗余 (容錯移轉叢集實例 (FCI)) 提供本機高可用性。 FCI 是在整個 Windows Server 容錯移轉叢集 (WSFC) 節點上安裝的單一 SQL Server 實例, 也可能跨多個子網。
  
如需詳細資訊, 請參閱[在商務用 Skype Server 2015 中規劃高可用性和災害復原](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>針對內部部署伺服器的集中式記錄及疑難排解改良功能

集中式記錄服務是商務用 Skype Server 2015 的首選記錄環境。 此版本中沒有新功能, 但已改善服務與集中式記錄服務代理程式 (ClsAgent) 的可靠性和效能, 這些是與控制器進行通訊的服務可執行檔, 而且會接收到的命令由管理員所頒發。
  
商務用 Skype Server 2015 使用 Windows PowerShell Cmdlet 來記錄管理服務代理程式、啟動追蹤, 並產生報告。 (Lync Server 2013 使用 ClsController 來執行這些任務)。
  
集中式記錄服務可以在任何商務用 Skype Server 2015 上執行。 內建的案例 (預先定義的追蹤) 保持不變, 就像建立自訂案例的能力一樣。 有一個稱為 AlwaysOn 的特殊案例一直在執行, 並允許系統管理員在近時間內找到一般問題。
  
Snooper 調試工具也已更新, 以允許調試行動裝置記錄, 並可與連接至 Lync 2013 或商務用 Skype Server 2015 的裝置搭配使用。 此工具可從 [[調試工具](https://go.microsoft.com/fwlink/?LinkId=285257)] 的網頁下載中取得。
  
## <a name="hybrid-deployment-and-management"></a>混合式部署與管理

商務用 Skype Server 2015 提供下列功能, 以啟用混合式部署管理和管理功能:
  
- 根據客戶內部部署資產的狀態進行混合式部署的建議 (由 O365 自動協助工具的 OnRamp 所決定)。
- 增強商務用 Skype Server 的 [控制台] 和 [商務用 Skype Server 系統管理中心] 的功能, 讓系統管理員可以使用這些工具來管理混合式部署。
- [控制台] 增強功能可讓系統管理員使用混合式設定向導登入 O365 租使用者, 並使用商務用 Skype Online 設定混合式。
- 可將內部部署使用者移至商務用 Skype Online 或將商務用 Skype Online 使用者移回內部部署的 [控制台] 支援。
- [控制台] 功能可識別及篩選從內部部署使用者移至商務用 Skype Online (也就是混合式使用者) 的內部部署使用者物件。
- 系統管理中心功能可在從內部部署到線上的混合式使用者中, 識別及篩選最初在商務用 Skype Online 中建立的雲端使用者。
- 使用 [控制台] 管理混合式使用者的功能, 可讓您從內部部署管理屬性, 以及從商務用 Skype Online 管理屬性的系統管理中心。
- 將密碼同步處理與 DirSync 結合使用, 可將內部部署的 Active Directory 密碼與線上租使用者進行同步處理。 如果已設定, 這項功能將會移除針對同盟驗證部署 AD FS 的需求, 但對於多重要素驗證, 仍需要 AD FS。 
- 持續支援商務用 Skype Online 與 Exchange 內部部署之間的共存。
    
> [!NOTE]
> Lync Online 2013 與 Exchange 內部部署共存及支援經驗沒有任何變更。 
  
## <a name="multi-factor-authentication"></a>多重要素驗證

多重要素驗證是一種驗證方法, 需要使用多個驗證方法, 並在使用者登入和事務中加入一個重要的第二層安全性。 例如, 需要使用者名稱和密碼及憑證。 商務用 Skype Server 2015 仍在 Lync Server 2013 累計更新中提供的多重要素驗證功能上建立。 多重要素驗證的重大變更如下:
  
- 使用 Office 2013 SP1 Active Directory 驗證庫與 Exchange 與 SharePoint 整合
- 商務用 Skype Web App 用戶端的多重要素驗證功能支援
    
在商務用 Skype 多重要素驗證中, 現在可以根據地理位置提供不同的驗證選項。 例如, 客戶可以設定其環境, 讓內部驗證依賴整合式 Windows 驗證, 而從組織外部進行驗證的員工則使用多重要素驗證。 
  
商務用 Skype 的多重要素驗證體驗是無縫的, 無論:
  
- 地理位置-使用者是否正在從組織內部或外部登入 
- 用戶端/裝置類型-使用哪一種商務用 Skype 用戶端, 以及用戶端正在執行的裝置 (PC、mobile、iPad 等)。
- [帳戶位置]-使用者是裝載于內部部署的 Active Directory 或 Azure Active Directory Online (O365)
