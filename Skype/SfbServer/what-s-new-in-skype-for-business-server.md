---
title: 商務用 Skype Server 2015 的新功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 2015 中的新功能。 如需有關新用戶端體驗的詳細資訊，請參閱 Lync 現在是商務用 Skype--查看最近更新。
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827583"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的新功能

**摘要：** 閱讀此主題以瞭解商務用 Skype Server 2015 中的新功能。 如需有關新用戶端體驗的詳細資訊，請參閱 [Lync 現在是商務用 Skype--查看](https://go.microsoft.com/fwlink/p/?LinkId=529022)最近更新。
  
Lync 現在是商務用 Skype，這是一種通訊和共同作業平臺，可透過 Skype 使用企業級的安全性、合規性及控制，將體驗融入在一起。 商務用 Skype 提供功能，包括狀態、IM、語音和影片通話及線上會議。 商務用 Skype 可提供新的用戶端體驗、新的伺服器版本，以及 Microsoft 365 或 Office 365 中服務的更新。 如果您組織中的使用者已熟悉 Skype，他們將會欣賞商務用 Skype 的強大功能和簡潔性，以方便找到並與共同工作者連線。 如果您組織中的使用者已從 Lync 前往商務用 Skype，他們就會辨識已使用的所有功能，但在具有簡化的控制項和新新增的新介面中。 除了新的用戶端經驗之外，商務用 Skype Server 2015 還提供數項新功能，以提升內部部署伺服器和混合式解決方案的可管理性。
  
商務用 Skype Server 2015 中的新功能包括下列專案的增強功能：
  
- 使用者體驗  
- 語音和影片支援
- 行動支援
- 內部部署伺服器的管理
- 混合式解決方案的部署和管理
- 多重要素驗證支援
    
## <a name="user-experience"></a>使用者體驗

商務用 Skype 用戶端看起來非常類似 Skype 的使用版本，並使用相同的按鈕和圖示。 較少的功能表和更簡單的任務階層可讓使用者輕鬆地快速找到所需的控制項和命令。 
  
商務用 Skype 包括上述所述的新使用者經驗，以及先前發行的 Lync 2013 使用者經驗。 同時包含這兩個經驗，可讓企業控制新用戶端向外延展的處理常式和時機，以管理其使用者的變更。預設的使用者經驗取決於所使用伺服器的版本。 管理員使用 **Set-CsClientPolicy** Cmdlet 搭配 EnableSkypeUI 參數，選擇慣用的經驗。 如需設定用戶端經驗的詳細資訊，請參閱 [Configure client experience With 商務用 skype](deploy/deploy-clients/configure-the-client-experience.md) 和 [桌面用戶端功能比較（適用于商務用 skype](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)）。
  
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。 在您嘗試設定用戶端環境以使用 Lync 2013 用戶端之前，請檢查用戶端版本，以確保其不是以數位16開頭;例如： x.x.x。 
  
## <a name="voice-and-video-improvements"></a>語音和影片的增強功能

商務用 Skype Server 2015 包括語音和影片功能的增強功能，包括通話資料收集和分析，以及與協力廠商影片電話會議系統的互通性改進。
  
### <a name="call-data-collection-and-analysis"></a>呼叫資料收集和分析

「我的通話」功能可讓商務用 Skype Server 2015 系統管理員收集通話資料。 此功能僅適用于內部部署部署。 在完成通話後，系統會提示使用者進行調查。 如需詳細資訊，請參閱 [在商務用 Skype Server 2015 中評級我的通話](manage/health-and-monitoring/rate-my-call.md)。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>與協力廠商影片電話會議系統的互通性改進

影片的 (VIS) 會在商務用 Skype Server 和 Cisco Video 電話會議 (VTC) 系統之間充當仲介。 加入會議時，使用者現在可以選取 Cisco VTC 系統。 在內部部署部署中，會以獨立伺服器角色的方式，將影片 (VIS) 成為獨立伺服器角色。 如需詳細資訊，請參閱 [在商務用 Skype server 中規劃影片 Interop 伺服器 2015](plan-your-deployment/video-interop-server.md)。
  
### <a name="call-via-work"></a>從公司通話

「透過工作通話」功能可讓企業使用者撥打來自商務用 Skype 用戶端的語音通話。 當使用者進行語音通話時，它會從商務用 Skype 路由傳送至始發者的 PBX 或 PSTN 電話。 當發信方接聽電話後，就會將通話導向目的地號碼。 呼叫收件者的答案，並使用商務用 Skype 服務做為控制台來建立通話。 發信方可以從商務用 Skype 管理其目前狀態和通話控制。 伺服器管理員可以啟用和設定企業的「呼叫」。 如需詳細資訊，請參閱[使用商務用 Skype Server 2015 中的計畫呼叫。](plan-your-deployment/enterprise-voice-solution/call-via-work.md) 
  
## <a name="mobile-device-support-improvements"></a>行動裝置支援的增強功能

行動裝置支援的增強功能包含改進 Enterprise Edition 使用者行動體驗的功能，例如存取交談記錄和記錄資料、增強行動會議體驗，以及跨 Office 的單一登入支援。 此外，您還可以透過常見的應用程式架構，對 Android 支援、效能增強功能及功能進行改進，以簡化整合。 
  
> [!NOTE]
> Lync 2013 UCWA 伺服器必須升級為商務用 Skype Server 2015，以支援行動用戶端。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>現在行動裝置上可以使用伺服器端交談記錄

若要啟用對交談記錄、未接的 IM 及通話記錄資料的行動存取，此資訊的封存現在會透過伺服器處理所有行動用戶端。 IM 的自動接受功能可在行動使用者未立即回應 IM 時，防止伺服器的超時訊息，提高可靠性。 若要利用以伺服器為基礎的 Exchange/Outlook 資料夾整合，需要 Exchange Server 2013 或更新版本，以及更新的行動用戶端。 
  
### <a name="enhanced-meeting-experiences"></a>增強的會議體驗

桌面上可用的會議功能現在也可供行動使用者使用。 新功能包括：
  
- 非同步導覽共用 PowerPoint 內容
- 簡報者取得共用 PowerPoint 內容控制權的能力
- 簡報者的會議廳管理，可讓他們承認或拒絕參與者
    
### <a name="skype-for-business-on-android-improvements"></a>Android 的商務用 Skype 增強功能

Android 版商務用 skype 現在提供的功能類似于商務用 Skype on iOS 和商務用 Skype on Windows：
  
- 繼續或重新加入交談
- 啟用憑證和被動驗證
- 邀請其他人加入交談
- 輕鬆開始群組交談
- 加入會議，而不是商務用 Skype 使用者
- 在 Android 平板電腦上啟用 smartphone 使用者介面
- 新增或移除參與者以管理會議
    
> [!NOTE]
> 這些功能需要 Android 作業系統版本4.0 或更新版本。 
  
## <a name="management-of-on-premises-servers"></a>內部部署伺服器的管理

商務用 Skype Server 2015 提供數項新功能，以提升內部部署伺服器的可管理性，包括就地升級、智慧安裝、改進的修補程式和升級程式、改進的前端集區冷啟動功能、SQL Server AlwaysOn 支援，以及集中式記錄與疑難排解。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>內部部署伺服器的就地升級

您現在可以使用全新的「就地升級」功能（使用現有的 Lync Server 2013 硬體和伺服器投資）將 Lync Server 2013 系統升級為商務用 Skype Server 2015，進而降低部署商務用 Skype 2015 Server 的整體成本。
  
就地升級有兩個案例：移動使用者方法（不需要停機）和離線方法（需要停機時間）。 如需適用于企業的升級程式的詳細資訊，請參閱 [規劃升級至商務用 Skype Server 2015](plan-your-deployment/upgrade.md)。 
  
> [!NOTE]
> 如果您是從 Lync Server 2010 升級，則無法使用就地選項。 如需從 Lync Server 2010 升級的詳細資訊，請參閱 [規劃升級至商務用 Skype Server 2015](plan-your-deployment/upgrade.md)。 
  
### <a name="smart-setup"></a>智慧安裝

自動偵測和下載更新的智慧安裝功能現在是安裝程式的一部分。 在安裝過程中，會詢問使用者安裝程式是否應該檢查更新。 如需詳細資訊，請參閱 [安裝商務用 Skype Server 2015](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>改進的前端伺服器修補和升級程式

商務用 Skype 伺服器引進兩個新的 Cmdlet，可協助升級或修補前端伺服器，比舊版 Lync Server 更輕鬆。
  
當您需要對前端伺服器套用修補程式或執行任何其他維護時，只要輸入 **CsComputerFailOver** ，並指定該伺服器的名稱即可。 商務用 Skype Server 會將該伺服器的工作負載臨時移至集區中的其他伺服器。 接著您可以執行維護，然後使用 **CsComputerFailback** 指令程式將該伺服器傳回服務。 如果您需要修補集區中的每一部伺服器，只要對每一部伺服器執行一次此程式，一次一個。 這些新的 Cmdlet 可讓您將伺服器的修補速度提高到舊版，以及更高的可靠性和較簡單的工作流程。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>改進的前端集區冷啟動功能

商務用 Skype 伺服器引進新的指令程式，可簡化及改善冷啟動整個前端集區的程式。 當您使用新的 **get-cspool** Cmdlet 時，它會檢查集區中所有前端伺服器的必要條件，然後嘗試啟動每一部伺服器。 如果遇到任何問題，它會進行診斷，並提醒您詳細資料和解決方法。 在某些情況下，即使有些個別的伺服器無法啟動，也可讓您啟動集區。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>內部部署伺服器的 SQL Server AlwaysOn 支援

商務用 Skype Server 2015 新增對 SQL Server AlwaysOn 可用性群組和 SQL Server AlwaysOn 容錯移轉叢集實例的支援。 除了這些功能之外，商務用 Skype Server 仍可繼續支援資料庫鏡像和 SQL Server 叢集，就像在舊版的 Lync Server 中一樣。
  
SQL Server AlwaysOn 可用性群組是 SQL Server 2012 和 SQL Server 2014 中的高可用性和嚴重損壞修復解決方案，可提供資料庫鏡像的替代方法。 可用性群組支援一組分立的資料庫容錯移轉環境 (稱為可用性資料庫) 一起進行容錯移轉。 可用性群組支援一組可讀寫的主資料庫，以及一到四組對應次要資料庫。 另外，次要資料庫可供唯讀存取和某些備份作業使用。
  
SQL Server 容錯移轉叢集實例利用 Windows Server 容錯移轉叢集 (WSFC) 功能，透過伺服器實例層級的冗余（容錯移轉叢集實例 (FCI) ）提供本機高可用性。 FCI 是安裝在 Windows Server 容錯移轉叢集 (WSFC) 節點上的單一 SQL Server 實例，而且可能會跨越多個子網。
  
如需詳細資訊，請參閱 [在商務用 Skype Server 2015 中規劃高可用性和嚴重損壞修復](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>內部部署伺服器的集中式記錄及疑難排解改進功能

集中式記錄服務是商務用 Skype Server 2015 的慣用記錄環境。 此版本沒有任何新功能，但已改進服務和集中式記錄服務代理程式的可靠性和效能 ( # A0) --與控制器通訊的服務可執行檔，且會接收系統管理員所發出的命令。
  
商務用 Skype Server 2015 使用 Windows PowerShell Cmdlet 來記錄管理服務代理程式、啟動追蹤並產生報告。  (Lync Server 2013 使用 ClsController.exe 來執行這些工作。 ) 
  
集中式記錄服務可以在任何商務用 Skype Server 2015 上執行。  (預先定義追蹤的內建案例) 保持不變，也就是建立自訂案例的功能。 有一個稱為「AlwaysOn 永遠執行」的特殊案例，可讓系統管理員在近即時找到常見問題。
  
Snooper 調試工具也已更新為允許調試行動性記錄檔，並且會與連接至 Lync 2013 或商務用 Skype Server 2015 的裝置搭配運作。 您可以從 [調試工具](https://go.microsoft.com/fwlink/?LinkId=285257)下載工具。
  
## <a name="hybrid-deployment-and-management"></a>混合式部署和管理

商務用 Skype Server 2015 會引入下列功能，以啟用混合式部署管理和管理功能：
  
- 根據客戶內部部署資產狀態的混合式部署的建議，取決於 Office 365 自動化協助工具的 OnRamp。
- 商務用 Skype Server 控制台和商務用 Skype Server 系統管理中心的增強功能，讓系統管理員可以使用這些工具來管理混合部署。
- 控制台增強功能可讓系統管理員使用混合式設定向導登入 Microsoft 365 或 Office 365 租使用者，並設定與商務用 Skype Online 的混合搭配。
- 控制台支援，可將內部部署使用者移至商務用 Skype Online，或將商務用 Skype Online 使用者移回內部部署。
- 控制台的功能可識別及篩選已移至商務用 Skype Online (也就是說，混合式使用者) 來自內部部署使用者的內部部署使用者物件。
- 系統管理中心功能，可從內部部署至線上的混合使用者，識別及篩選最初在商務用 Skype Online 中建立的雲端使用者。
- 使用控制台管理混合式使用者的能力，可從內部部署和管理中心取得可從商務用 Skype Online 管理的屬性。
- 使用與 DirSync 的密碼同步處理與線上承租人同步處理內部部署 Active Directory 密碼的功能。 若設定，這項功能將不再需要部署 AD FS 以進行同盟驗證，但多重要素驗證仍需要 AD FS。 
- 持續支援商務用 Skype Online 與 Exchange 內部部署之間的共存。
    
> [!NOTE]
> Lync Online 2013 和 Exchange 內部部署共存和支援經驗沒有任何變更。 
  
## <a name="multi-factor-authentication"></a>多重要素驗證

多重要素驗證是一種驗證方法，需要使用多個驗證方法，並為使用者登入和交易新增一個重要的第二層安全性。 例如，需要使用者名稱和密碼，以及憑證。 商務用 Skype Server 2015 仍在 Lync Server 2013 累計更新中提供的多重要素驗證功能上建立。 多重要素驗證中的重大變更如下：
  
- 使用 Office 2013 SP1 Active Directory 驗證程式庫與 Exchange 及 SharePoint 整合
- 支援商務用 Skype Web App 用戶端中的多重要素驗證功能
    
透過商務用 Skype 多重要素驗證，現在可以根據地理位置提供不同的驗證選項。 例如，客戶可以設定其環境，讓內部驗證依賴整合式 Windows 驗證，而從組織外部進行驗證的員工則使用多重要素驗證。 
  
商務用 Skype 多重要素驗證體驗不論是什麼，都是無縫的：
  
- 地理位置-使用者是否從組織內部或外部登入 
- 用戶端/裝置類型-使用哪一種商務用 Skype 用戶端，以及用戶端在哪個裝置上執行 (電腦、mobile、iPad 等等 ) 
- 帳戶位置-使用者是否主控于內部部署 Active Directory 或 Azure Active Directory Online 中。
