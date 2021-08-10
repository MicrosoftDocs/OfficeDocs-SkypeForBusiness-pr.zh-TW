---
title: 測試商務用 Skype Server 中的系統管理員許可權
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如何在商務用 Skype Server 中測試系統管理員許可權
ms.openlocfilehash: 1c828eeb965ee98aae72b00c7da9fa65016d2ed90e56c7cc982a59763c2703ae
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590767"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>測試商務用 Skype Server 中的系統管理員許可權

|&nbsp; |&nbsp; |
|--|--|
|驗證排程|初始商務用 Skype Server 部署之後。 在發生許可權相關的問題時，視需要進行。|
|測試控管|Windows PowerShell|
|必要的權限|當您使用商務用 Skype Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。<br><br/>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsOUPermission Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示中執行下列命令：<br/><br/>Get-CsAdminRole \| Where-Object {$ _。Cmdlet-符合 "Test-CsOUPermission"}|
|||

## <a name="description"></a>描述

當您安裝商務用 Skype Server 時，安裝程式執行的其中一個工作會讓 RTCUniversalUserAdmins 群組管理使用者、電腦、連絡人、應用程式連絡人及 InetOrg 人員所需的 Active Directory 許可權。 如果您已在 Active Directory 中停用許可權繼承，安裝程式將無法指派這些許可權。 因此，RTCUniversalUserAdmins 群組的成員將無法管理商務用 Skype Server 實體。 只有網域系統管理員可以使用這些管理許可權。 

Test-CsOUPermission Cmdlet 會驗證管理使用者、電腦及其他物件所需的必要許可權是否已在 Active Directory 容器上設定。 若未設定這些許可權，您可以執行 [Grant-CsOUPermission Cmdlet](/powershell/module/skype/Grant-CsOUPermission)來解決此問題。 

請注意，Grant-CsOUPermission 只能將許可權指派給 RTCUniversalUserAdmins 群組的成員。 您無法使用此 Cmdlet 將許可權授與任意使用者或群組。 若要讓不同的使用者或群組擁有使用者管理許可權，您應該將該使用者 (或群組) 新增至 RTCUniversalUserAdmins 群組。 


## <a name="running-the-test"></a>執行測試

若要確認是否已在容器上設定管理許可權，請先執行 Test-CsOUPermission 指令程式，然後再執行容器的辨識名稱，以及您要驗證的許可權類型。 例如，此命令會檢查是否已在 OU ou = Redmond，dc = litwareinc，dc = com 上設定使用者許可權：

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

若要使用單一命令來驗證多個許可權，請以引號括住每個許可權類型，然後使用逗號分隔這些類型。 例如，下列命令會驗證使用者、電腦及連絡人許可權：

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

如需詳細資訊，請參閱 [Test-CsOUPermission Cmdlet](/powershell/module/skype/test-csoupermission)的 [說明] 主題。

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已設定必要的許可權，Test-CsOUPermission 會傳回一個單字回應：

True

如果未設定必要的許可權，Test-CsOUPermission 會傳回值 False。 您可能需要搜尋一會兒，以找出此值。 它通常會內嵌在數個伴隨的警告內。 例如：

警告：存取控制專案 (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;供ReadProperty;ContainerInherit;其子bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告：物件 "OU = NorthAmerica，DC = atl-cs-001\DC = litwareinc，DC=com" 的存取控制專案 (Ace) 尚未就緒。 

False 

警告： "Test-CsOUPermission" 處理已完成，但有警告。 在此執行期間，記錄了 "2" 個警告。 

警告：在 "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" 可以找到詳細的結果。 

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 Test-CsOUPermission 失敗，通常表示指定的許可權尚未指派給 RTCUniversalUserAdmins 群組。 您可以使用 Grant-CsOUPermission Cmdlet 來解決此問題，並指派必要的許可權。 例如，下列命令會將使用者、連絡人及 Inetorgperson 的 OU 許可權提供給 RTCUniversalUserAdmins 群組：

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

如需詳細資訊，請參閱 [Test-CsOUPermission Cmdlet](/powershell/module/skype/test-csoupermission)的 [說明] 主題。