---
title: 安裝及開啟系統管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本主題說明如何安裝及開啟您部署及管理商務用 Skype 所需的系統管理工具。
ms.openlocfilehash: 70f7732c9db49f5a089e9d5008a27902e5aac51c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630477"
---
# <a name="install-and-open-administrative-tools"></a>安裝及開啟系統管理工具

本主題說明如何安裝部署及管理商務用 Skype Server 所需的系統管理工具。 預設會在執行商務用 Skype Server 的每一部伺服器上安裝系統管理工具。 此外，您也可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。 強烈建議您在與所建立的商務用 Skype Server 部署相同的網域或樹系中的電腦上安裝系統管理工具，以確保 Active Directory 網域服務準備步驟已完成，這可讓您稍後在該電腦上使用系統管理工具來發佈拓撲。 此外，請務必先複查必要的需求，再安裝或使用商務用 Skype Server 系統管理工具。 請參閱[商務用 Skype Server 2019](../../SfBServer2019/plan/system-requirements.md)或[商務用 Skype Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)中的需求檔。
 
> [!Important]
> 如果您的組織需要在系統磁片磁碟機以外的磁片磁碟機上，找到 Internet Information Services (IIS) 和所有 Web 服務，您可以在 [安裝程式] 對話方塊中變更商務用 Skype Server 檔案的安裝位置路徑。 若將安裝檔案安裝至此路徑（包括 OCSCore.msi），其餘的商務用 Skype Server 檔案也會同時部署至此磁片磁碟機。 

## <a name="to-install-the-administrative-tools"></a>安裝系統管理工具

1. 以本機系統管理員身分登入，將 (最低需求) 至您要安裝系統管理工具的電腦。 如果您在 Windows 和使用者帳戶控制中以標準使用者的身分登入 (啟用 UAC) ，系統會提示您輸入本機系統管理員或網域對等的使用者名稱和密碼。
2. 在電腦上找出安裝媒體，然後按兩下 [\Setup\amd64\Setup.exe]。
3. 如果系統提示您安裝 Microsoft Visual C++ 可發佈的，請按一下 **[是]**。
4. 在 [安裝位置] 頁面上，按一下 **[確定]**。 如果您需要將檔案安裝至其他位置，請將此路徑變更為其他位置或磁碟機。

    > [!Important]
    > 如果您的組織需要在系統磁片磁碟機以外的磁片磁碟機上，找到 Internet Information Services (IIS) 和所有 Web 服務，您可以在 [安裝程式] 對話方塊中變更商務用 Skype Server 檔案的安裝位置路徑。 若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其餘的商務用 Skype Server 檔案也會部署至此磁片磁碟機。 

5. 在 [使用者授權合約] 頁面上檢閱授權條款，然後依序按一下 **[我接受]** 和 **[確定]**。需要完成此步驟才能繼續。
6. 在 [部署嚮導] 頁面上，按一下 [ **安裝系統管理員工具**]。 
7. 當安裝順利完成時，按一下 **[結束]**。

使用下列程式開啟系統管理工具，以部署、設定或疑難排解商務用 Skype Server 拓撲。

- [部署嚮導](#deployment-wizard)
- [拓撲產生器](#topology-builder) 
- [商務用 Skype Server 控制台](#skype-for-business-server-control-panel)
- [商務用 Skype Server 管理命令介面](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>部署嚮導

請使用下列程式在本機啟動部署嚮導，以新增或移除元件檔案。

**啟動商務用 Skype Server 部署嚮導**

1. 以 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的身分，登入安裝商務用 Skype Server 部署嚮導的電腦。
2. 依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 部署嚮導]**。


## <a name="topology-builder"></a>拓撲產生器 

使用下列程式開啟拓撲產生器，以定義您想要在商務用 Skype Server 拓撲中部署的伺服器。

**若要開啟商務用 Skype Server 拓撲產生器以設計拓撲**

1. 以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。
    > [!NOTE]
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，但可讀取、發佈或啟用拓撲，這是在伺服器上安裝商務用 Skype Server 所需的。您必須使用屬於 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，而且在要用於封存檔案存放區的檔案共用上具有「完全控制」許可權 (（即讀取、寫入及修改），讓拓撲產生器可以設定必要的自由存取控制清單 (dacl) ，或具有同等使用者權限的帳戶。) 
 
2. 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 拓撲** 產生器]。

## <a name="skype-for-business-server-control-panel"></a>商務用 Skype Server 控制台 

使用下列其中一個程式來開啟商務用 Skype Server 控制台，以管理環境中的伺服器、使用者、用戶端和裝置的設定。

> [!NOTE]
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶，在商務用 Skype Server 控制台中執行任何工作。 您可以使用其他角色登入商務用 Skype Server 控制台，以執行特定的管理工作，取決於您需要執行的任務。 例如，您可以使用 CSArchivingAdministrator 管理商務用 Skype Server 控制台中的封存。 如需角色的詳細資訊，請參閱 [規劃角色型存取控制](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。 如需您可以用來執行特定工作的角色的詳細資訊，請參閱任務的檔。 

**從組織防火牆內部的任何電腦開啟商務用 Skype Server 控制台**

1. 從指派給要執行之工作的 CsAdministrator 角色或其他角色的使用者帳戶，登入內部部署中的任何電腦，最小螢幕解析度為 1024 x 768。

    > [!IMPORTANT]
    > 如果您已將管理簡單的統一資源定位器設定 (URL) ，您可以從組織防火牆內任何電腦上執行的網際網路瀏覽器，存取商務用 Skype Server 控制台。 如需設定管理簡易 URL 的詳細資訊，請參閱 [規劃簡易 URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) 及 [編輯或設定簡單 URLs](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls)。 

2. 開啟瀏覽器視窗，然後輸入為您的組織設定的管理 URL。

**在執行商務用 Skype Server 的電腦上開啟商務用 Skype Server 控制台**

1. 從屬於 CsAdministrator 角色的成員或其他角色的使用者帳戶，其具有要執行之工作的適當使用者權限及許可權，登入已安裝商務用 Skype Server 的電腦，至少商務用 Skype Server 系統管理工具。 若要設定設定，電腦必須具有 1024 x 768 的最小螢幕解析度。
2. 開始商務用 Skype Server 控制台：按一下 [**開始**]，按一下 [**所有程式**]，指向 [系統 **管理工具**]，指向 [**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 控制台**]。

## <a name="skype-for-business-server-management-shell"></a>商務用 Skype Server 管理命令介面 

使用下列程式，開啟使用命令列來管理環境中的伺服器、使用者、用戶端和裝置的商務用 Skype Server 管理命令介面。

> [!NOTE]
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶，在商務用 Skype Server 管理命令介面中執行任何工作。 您可以使用其他角色登入，以執行特定的管理工作，取決於您需要執行的工作。 例如，您可以使用 CSArchivingAdministrator 來執行與封存管理相關的 Cmdlet。 如需角色的詳細資訊，請參閱 [規劃角色型存取控制](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。 如需您可以用來執行特定 Cmdlet 的角色的詳細資訊，請參閱 Cmdlet 的檔。<br/><br/>您也可以使用 RTCUniversalServerAdmins、RTCUniversalUserAdmins 或 RTCUniversalReadOnlyAdmins 群組中的使用者帳戶來執行某些 Cmdlet，視 Cmdlet 而定。 

**開啟商務用 Skype Server 管理命令介面**

如果您開啟的是 Windows PowerShell 的視窗，而不是商務用 Skype Server 管理命令介面，則根據預設，您無法執行商務用 Skype Server Cmdlet。 若要從 Windows PowerShell 中執行商務用 Skype Server Cmdlet，請在 Windows PowerShell 命令提示字元處輸入下列命令：

`Import-Module Lync`

啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。