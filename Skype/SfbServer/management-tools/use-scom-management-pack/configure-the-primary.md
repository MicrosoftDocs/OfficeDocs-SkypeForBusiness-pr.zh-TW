---
title: 設定主要管理伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 摘要：設定您的主要管理伺服器、安裝 System Center Operations Manager，以及匯入商務用 Skype Server 2015 的管理套件。
ms.openlocfilehash: ace25e1b4971c561dc1544290b04f481f36c9676
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111639"
---
# <a name="configure-the-primary-management-server"></a>設定主要管理伺服器

**摘要：** 設定您的主要管理伺服器、安裝 System Center Operations Manager，以及匯入商務用 Skype Server 2015 的管理套件。

若要充分利用商務用 Skype Server 2015 中包含的新狀況監視功能，您必須先指定一部電腦做為您的主要管理伺服器。 接著，您必須在該電腦上安裝 System Center Operations Manager 2012 SP1 或 R2 或 System Center Operations Manager 2007 R2。 此外，您必須先安裝支援版本的 SQL Server，才能充當 Operations Manager 後端資料庫。

當您安裝 System Center Operations Manager 時，您將需要安裝該產品的所有元件，包括：

- 操作資料庫

- 伺服器

- 主控台

- Windows PowerShell Cmdlet

- Web 主控台

- 報告

- 資料倉儲

> [!IMPORTANT]
> 安裝 System Center Operations Manager 2012 之前，必須先安裝「[Microsoft Report Viewer 2010 可轉散發元件套件](https://www.microsoft.com/download/details.aspx?id=6442)」。

如需這些產品及其安裝的詳細資訊，請參閱下列連結：

- [System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Configuration Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

請記住，每個商務用 Skype Server 部署只能有一個根管理伺服器。

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>匯入商務用 Skype Server 2015 管理套件

您可以安裝管理套件（會決定 System Center operations Manager 可監控哪些專案、應如何監視這些專案，以及如何觸發及報告提醒）的軟體，以擴充 System Center Operations Manager 的功能。 商務用 Skype Server 2015 包括兩個 System Center Operations Manager 管理元件，可提供下列功能：

- **Component 和 User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) 會追蹤事件記錄檔中記錄的商務用 Skype Server 問題、由效能計數器所註冊，或是記錄在詳細通話記錄 (cdr) 或經驗品質 (QoE) 資料庫。 針對嚴重問題，您可以設定 System Center Operations Manager 立即透過電子郵件、立即訊息或 SMS 訊息通知系統管理員。  (短信或短訊息服務是用來將文字訊息從一部行動裝置傳送至另一部行動裝置的技術。 ) 

    > [!NOTE]
    >  如需設定 Operations Manager 通知的詳細資訊，請參閱設定 [通知](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))。

- **使用中的 Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) 主動測試重要的商務用 Skype Server 元件，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。 這些測試是透過商務用 Skype Server 綜合交易 Cmdlet 來執行。 例如， **Test-CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。 如果此模擬交談失敗，就會產生警示。

匯入管理套件是一個重要的步驟。 若未匯入管理套件，您將無法使用 Operations Manager 來監視商務用 Skype 伺服器事件或執行商務用 Skype Server 綜合交易。

元件和使用者管理套件只會用來監視商務用 Skype Server 2015。 如果您處於同時安裝商務用 Skype Server 2015 和 Lync Server 2013 的共存案例中，您應該繼續使用 Lync server 2013 管理元件來進行 Lync Server 2013 電腦。

> [!NOTE]
> 商務用 Skype Server 2015 的管理元件包括商務用 Skype Server 2015 元件、使用者管理套件和商務用 Skype Server 2015 使用中監控管理元件。

您可以使用下列其中一個工具匯入管理元件：

- **System Center Operations Manager** 使用此方法，您可以使用 Operations Manager 為商務用 Skype Server 新增監控。

- **Operations Manager 命令** 介面您可以使用 Operations Manager 命令介面直接匯入，或疑難排解使用 System Center Operations Manager 主控台匯入管理元件時所遇到的任何問題。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 匯入管理套件

1. 從 Microsoft Web 下載下載 SkypeForBusiness2015ManagementPacks.msi，然後安裝 msi。

2. 在 System Center Operations Manager 中，按一下 [ **管理**]。

3. 在 [管理] 窗格中，以滑鼠右鍵按一下 [ **管理元件**]，然後按一下 [匯 **入管理元件**]。

4. 在 [ **選取管理元件** ] 對話方塊中，按一下 [ **新增**]，然後按一下 [ **從磁片新增**]。

5. 在 [ **線上目錄連線** ] 對話方塊中，按一下 [ **否**]。

6. 在 [ **選取要匯入的管理元件** ] 對話方塊中，找出並選取 [檔案 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp] 和 [Microsoft.LS.2015.Monitoring.ComponentAndUser.mp]，然後按一下 [ **開啟**]。 若要在對話方塊中選取多個檔案，請按一下第一個檔案，然後按住 Ctrl 鍵並按一下後續的檔案。

7. 在 [ **選取管理元件** ] 對話方塊中，按一下 [ **安裝**]。 如果您收到錯誤訊息，且安裝失敗，這通常表示管理元件檔案位於由 Windows 使用者帳戶控制保護的資料夾中。 如果發生這種情況，請將檔案複製到其他資料夾，然後重新開機匯入和安裝程式。

8. 在 [ **選取管理元件** ] 對話方塊中，按一下 [ **關閉**]。 匯入和安裝程式可能需要數分鐘才能完成。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 命令介面匯入管理套件

一般說來，使用 Operations Manager 主控台匯入管理元件會比較容易。 不過，如果發生錯誤，而且匯入失敗，則主控台不一定會提供適當的錯誤報表。 依比較，Operations Manager 命令介面會提供詳細資訊。 如果您使用的是 Operations Manager，而且在匯入管理元件時遇到問題，請使用 Operations Manager 命令介面匯入套裝軟體。 Operations Manager 命令介面提供的資訊可協助您決定匯入失敗的原因。

1. 依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft System Center 2012**] 及 [ **Operations Manager**]，然後按一下 [ **operations manager 命令** 介面]。

2. 在 Operations Manager 命令介面中，使用您的檔案 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 副本的實際路徑，在命令提示字元處輸入下列命令，然後按 ENTER：

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. 在匯入第一個管理套件之後，請使用您的檔案 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 副本的路徑重複此程式：

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```