---
title: 設定主要管理伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: '摘要: 設定您的主要管理伺服器、安裝 System Center Operations Manager, 並匯入商務用 Skype Server 2015 的管理套件。'
ms.openlocfilehash: a89ee8ca7c7f5601d9219ef49643adc2ebf99883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187942"
---
# <a name="configure-the-primary-management-server"></a>設定主要管理伺服器

**摘要:** 設定您的主要管理伺服器、安裝 System Center Operations Manager, 並匯入商務用 Skype Server 2015 的管理套件。

若要充分利用商務用 Skype Server 2015 中包含的新健康情況監視功能, 您必須先指定電腦作為您的主要管理伺服器。 接著, 您必須在該電腦上安裝 System Center Operations Manager 2012 SP1 或 R2 或 System Center Operations Manager 2007 R2。 此外, 您必須先安裝支援的 SQL Server 版本, 才能充當 Operations Manager 後端資料庫。

當您安裝 System Center Operations Manager 時, 您必須安裝該產品的所有元件, 包括:

- 運算元據庫

- 伺服器

- 控制

- Windows PowerShell Cmdlet

- 網頁主控台

- 舉報

- 資料倉儲

> [!IMPORTANT]
> 您必須先安裝 [[Microsoft 報表檢視器2010可轉散發元件套件](https://www.microsoft.com/en-us/download/details.aspx?id=6442)], 才能安裝 System Center Operations Manager 2012。

如需這些產品及其安裝的詳細資訊, 請參閱下列連結:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

請記住, 每個商務用 Skype Server 部署只能有一個根管理伺服器。

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>匯入商務用 Skype Server 2015 管理套件

您可以透過安裝管理套件來延伸 System Center Operations Manager 的功能, 此軟體會指示 System Center Operations Manager 可以監視哪些專案、應如何監視這些專案, 以及應如何觸發預警, 以及曾. 商務用 Skype Server 2015 包含兩個系統中心作業管理員管理套件, 可提供下列功能:

- **元件與使用者管理套件**(Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) 追蹤事件日誌中記錄的商務用 Skype 伺服器問題、由效能計數器所註冊, 或記錄在通話詳細資料記錄 (CDRs) 或體驗品質 (QoE) 資料庫中。 針對重要問題, 系統中心作業管理員可以設定為透過電子郵件、立即訊息或 SMS 訊息立即通知管理員。 (SMS 或短訊息服務) 是用來將文字訊息從一部行動裝置傳送至另一部的技術。

    > [!NOTE]
    >  如需有關設定 Operations Manager 通知的詳細資訊, 請參閱設定[通知](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。

- **主動監視管理套件**(Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) 前瞻性地測試商務用 Skype Server 元件, 例如登入系統、交換立即訊息, 或撥打電話至位於公用交換電話網絡 (PSTN). 這些測試是使用商務用 Skype Server 綜合交易 Cmdlet 進行。 例如, **CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。 如果這個模擬交談失敗, 就會產生警示。

匯入管理套件是一個重要的步驟。 如果不是匯入管理套件, 您將無法使用 Operations Manager 來監控商務用 Skype 伺服器事件, 或執行商務用 Skype Server 綜合交易。

元件與使用者管理套件只用來監控商務用 Skype Server 2015。 如果您在已安裝商務用 Skype Server 2015 和 Lync Server 2013 的共存案例中, 您應該繼續針對 Lync Server 2013 電腦使用 Lync Server 2013 管理套件。

> [!NOTE]
> 商務用 Skype Server 2015 的管理套件包括商務用 Skype Server 2015 元件與使用者管理套件, 以及商務用 Skype Server 2015 活動的監視管理套件。

您可以使用下列其中一個工具匯入管理套件:

- **System Center Operations Manager**使用這個方法, 您可以使用 Operations Manager 來新增商務用 Skype Server 的監視。

- **Operations Manager 命令**介面您可以使用 Operations Manager Shell 直接匯入, 或針對您使用 System Center Operations Manager 主控台匯入管理套件時所遇到的任何問題進行疑難排解。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 匯入管理套件

1. 從 Microsoft Web 下載下載 SkypeForBusiness2015ManagementPacks, 然後安裝 msi。

2. 在系統中心作業管理員中, 按一下 [**管理**]。

3. 在 [管理] 窗格中, 以滑鼠右鍵按一下 [**管理套件**], 然後按一下 [匯**入管理套件**]。

4. 在 [**選取管理套件**] 對話方塊中, 按一下 [**新增**], 然後按一下 [**從磁片新增**]。

5. 在 [**線上目錄連線**] 對話方塊中, 按一下 [**否**]。

6. 在 [**選取要匯入的管理套件**] 對話方塊中, 找出並選取 [檔案] Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, 然後按一下 [**開啟**]。 若要在對話方塊中選取多個檔案, 請按一下第一個檔案, 然後按住 Ctrl 鍵並按一下後續的檔案。

7. 在 [**選取管理套件**] 對話方塊中, 按一下 [**安裝**]。 如果您收到錯誤訊息, 且安裝失敗, 通常表示管理套件檔案位於受 Windows 使用者帳戶控制保護的資料夾中。 如果發生這種情況, 請將檔案複製到不同的資料夾, 然後重新開機匯入和安裝程式。

8. 在 [**選取管理套件**] 對話方塊中, 按一下 [**關閉**]。 匯入及安裝程式可能需要幾分鐘的時間才能完成。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 命令介面匯入管理套件

一般來說, 您可以使用 Operations Manager 主控台來輕鬆匯入管理套件。 不過, 如果發生錯誤, 並匯入失敗, 則主機不一定會提供足夠的錯誤報表。 根據比較, Operations Manager 命令介面會提供詳細資訊。 如果您使用的是 Operations Manager, 且在您匯入管理套件時遇到問題, 請使用 Operations Manager 命令介面匯入套件。 Operations Manager 命令介面提供的資訊可協助您判斷匯入失敗的原因。

1. 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft System Center 2012**], 再按一下 [ **Operations Manager**], 然後按一下 [ **operations manager 命令**介面]。

2. 在 Operations Manager Shell 中, 在命令提示字元中輸入下列命令, 並使用您的檔案 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 複本的實際路徑, 然後按 ENTER:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. 匯入第一個管理套件之後, 請使用您的 [檔案 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp] 複本路徑來重複此程式:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
