---
title: 安裝及開啟系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主題說明如何安裝及開啟部署和管理商務用 Skype 所需的管理工具。
ms.openlocfilehash: 612ea46fe8870944fa4b460b034bb9a7386a88bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186784"
---
# <a name="install-and-open-administrative-tools"></a>安裝及開啟系統管理工具

本主題說明如何安裝部署和管理商務用 Skype Server 所需的管理工具。 預設會在執行商務用 Skype Server 的每個伺服器上安裝系統管理工具。 此外, 您還可以在其他電腦上安裝系統管理工具, 例如專用的系統管理主控台。 我們強烈建議您在與您建立的商務用 Skype Server 部署相同網域或林中的電腦上安裝系統管理工具, 以確保 Active Directory 網域服務準備步驟已完成。這可讓您稍後在該電腦上使用 [管理工具] 發佈您的拓撲。 在安裝或使用商務用 Skype Server 管理工具前, 請務必先查看必要的需求。 請參閱[商務用 Skype server 2019](../../SfBServer2019/plan/system-requirements.md)或[商務用 skype server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)中的需求檔。
 
> [!Important]
> 如果您的組織要求您在系統磁片磁碟機以外的磁碟機上找到 [網際網路資訊服務 (IIS)] 和 [所有 Web 服務], 您可以在 [設定] 對話方塊中變更商務用 Skype Server 檔案的安裝位置路徑。 如果您將安裝檔案安裝到此路徑, 包括 OCSCore, 則其餘的商務用 Skype Server 檔案也會部署到這個磁片磁碟機。 

## <a name="to-install-the-administrative-tools"></a>若要安裝管理工具

1. 以本機系統管理員 (最小需求) 登入您想要安裝管理工具的電腦。 如果您是在 Windows 和使用者帳戶控制 (UAC) 中以標準使用者身分登入, 系統會提示您輸入本機系統管理員或網域對等的使用者名稱和密碼。
2. 在您的電腦上找出安裝媒體, 然後按兩下 [\Setup\amd64\Setup.exe.]。
3. 如果系統提示您安裝 Microsoft Visual c + + 可發佈專案, 請按一下 **[是]**。
4. 在 [安裝位置] 頁面上, 按一下 **[確定]**。 如果您需要將檔案安裝至其他位置, 請將此路徑變更為其他位置或磁片磁碟機。

    > [!Important]
    > 如果您的組織要求您在系統磁片磁碟機以外的磁碟機上找到 [網際網路資訊服務 (IIS)] 和 [所有 Web 服務], 您可以在 [設定] 對話方塊中變更商務用 Skype Server 檔案的安裝位置路徑。 如果您將安裝檔案安裝到此路徑, 包括 OCSCore, 則其餘的商務用 Skype Server 檔案也將會部署到此磁片磁碟機。 

5. 在 [使用者授權合約] 頁面上, 查看 [授權條款], 按一下 [**我接受**], 然後按一下 **[確定]**。 您必須先執行此步驟, 才能繼續進行。
6. 在 [部署嚮導] 頁面上, 按一下 [**安裝系統管理員工具**]。 
7. 安裝順利完成後, 請按一下****[結束]。

使用下列程式來開啟 [管理工具], 以部署、設定或疑難排解您的商務用 Skype Server 拓撲。

- [部署嚮導](#deployment-wizard)
- [拓撲建立器](#topology-builder) 
- [商務用 Skype Server 的 [控制台]](#skype-for-business-server-control-panel)
- [商務用 Skype Server 管理命令介面](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>部署嚮導

使用下列程式在本機啟動部署嚮導, 以新增或移除元件檔。

**啟動商務用 Skype Server 部署嚮導**

1. 登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝商務用 Skype Server 部署嚮導的電腦。
2. 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server**], 然後按一下 [**商務用 skype server 部署嚮導]**。


## <a name="topology-builder"></a>拓撲建立器 

使用下列程式開啟 [拓撲建立器], 以定義您想要在商務用 Skype Server 拓撲結構中部署的伺服器。

**開啟商務用 Skype Server 拓撲建立器以設計拓撲**

1. 登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。
    > [!NOTE]
    > 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴, 但若要讀取、發佈或啟用拓撲 (在伺服器上安裝商務用 Skype Server 所需), 您必須使用屬於 Domain Admins 群組成員的帳戶和第[e RTCUniversalServerAdmins] 群組, 且在您要用於封存檔案存放區的檔案共用上擁有 [完全控制] 許可權 (也就是讀取、寫入及修改), 讓拓撲建立器可以設定所需的隨機存取控制清單 (Dacl), 或是具有同等使用者權限的帳戶。
 
2. 啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server**], 然後按一下 [**商務用 skype server 拓撲**建立器]。

## <a name="skype-for-business-server-control-panel"></a>商務用 Skype Server 的 [控制台] 

使用下列其中一個程式來開啟商務用 Skype Server 的 [控制台], 在您的環境中管理伺服器、使用者、用戶端和裝置的配置。

> [!NOTE]
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶, 在商務用 Skype Server 的 [控制台] 中執行任何任務。 您可以使用其他角色登入商務用 Skype Server 的 [控制台] 來執行特定的系統管理工作, 視需要執行的工作而定。 例如, 您可以在商務用 Skype Server 的 [控制台] 中使用 CSArchivingAdministrator 來管理存檔。 如需有關角色的詳細資訊, 請參閱[規劃角色式存取控制](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)。 如需可用於執行特定工作之角色的詳細資訊, 請參閱該工作的相關檔。 

**若要從組織防火牆內的任何電腦開啟商務用 Skype Server 的 [控制台]**

1. 從指派給 CsAdministrator 角色的使用者帳戶, 或其他具有要執行之工作之許可權的角色, 請以最小的螢幕解析度 1024 x 768 登入內部部署中的任何電腦。

    > [!IMPORTANT]
    > 如果您已設定管理簡單的統一資源定位器 (URL), 您可以從您組織防火牆內任何電腦上執行的網際網路瀏覽器, 存取商務用 Skype Server 的 [控制台]。 如需有關設定管理簡單 URL 的詳細資料, 請參閱[規劃簡單的 url](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx)以及[編輯或設定簡單的 url](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx)。 

2. 開啟瀏覽器視窗, 然後輸入為貴組織設定的管理員 URL。

**若要在執行商務用 Skype Server 的電腦上開啟商務用 Skype Server 的 [控制台]**

1. 如果使用者帳戶是 CsAdministrator 角色的成員或其他角色, 且具有適當的使用者權利和許可權, 且有要執行的工作, 請登入您已安裝商務用 Skype Server 的電腦, 或者至少[商務用 Skype Server] 管理工具。 若要設定設定, 電腦的畫面解析度必須達到 1024 x 768 的最小值。
2. 啟動商務用 Skype Server 的 [控制台]: 按一下 [**開始**], 按一下 [**所有程式**], 指向 [系統**管理工具**], 指向 [**商務用 Skype 伺服器**], 然後按一下 [**商務用 skype server 控制台**]。

## <a name="skype-for-business-server-management-shell"></a>商務用 Skype Server 管理命令介面 

使用下列程式來開啟商務用 Skype Server Management Shell, 以在您的環境中使用命令列來管理伺服器、使用者、用戶端和裝置。

> [!NOTE]
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶, 在商務用 Skype Server Management 命令介面中執行任何任務。 您可以使用其他角色登入, 以執行特定的系統管理工作, 視您需要執行的任務而定。 例如, 您可以使用 CSArchivingAdministrator 來執行與封存管理相關的 Cmdlet。 如需有關角色的詳細資訊, 請參閱[規劃角色式存取控制](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)。 如需可用於執行特定 Cmdlet 之角色的詳細資訊, 請參閱 Cmdlet 的相關檔。<br/><br/>您也可以使用 [RTCUniversalServerAdmins]、[RTCUniversalUserAdmins] 或 [RTCUniversalReadOnlyAdmins] 群組中的使用者帳戶來執行某些 Cmdlet (視 Cmdlet 而定)。 

**開啟商務用 Skype Server 管理命令介面**

如果您開啟的是 Windows PowerShell 視窗, 而不是商務用 Skype Server Management Shell, 則預設不能執行商務用 Skype Server Cmdlet。 若要在 Windows PowerShell 中執行商務用 Skype Server Cmdlet, 請在 Windows PowerShell 命令提示字元輸入下列內容:

`Import-Module Lync`

啟動商務用 Skype Server 管理命令介面: 請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype 伺服器**], 然後按一下 [**商務用 skype server 管理命令**介面]。
