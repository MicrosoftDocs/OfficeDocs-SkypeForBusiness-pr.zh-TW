---
title: 測試商務用 Skype Server 中的系統管理員拓撲權力
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 如何在商務用 Skype Server 中測試拓撲權力
ms.openlocfilehash: 6f4eed0271d9dd6d099d19287f7caa37148f6026
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861310"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>測試商務用 Skype Server 中的系統管理員拓撲權力

|&nbsp; |&nbsp; |
|--|--|
|驗證排程|初始商務用 Skype Server 部署之後。 在發生許可權相關的問題時，視需要進行。|
|測試控管|Windows PowerShell|
|必要的權限|當您使用商務用 Skype Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。<br/><br/>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsSetupPermission Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示中執行下列命令：<br/><br/>Get-CsAdminRole \| Where-Object {$ _。Cmdlet-符合 "Test-CsSetupPermission"}|
|||

## <a name="description"></a>描述

根據預設，只有網域管理員可以啟用商務用 Skype Server 拓撲，並對商務用 Skype Server 基礎結構進行大型變更。 只要您的網域管理員和您的商務用 Skype Server 管理員是同一個，這就不是問題。 在許多組織中，商務用 Skype Server 管理員不會保留整個網域的系統管理許可權。 根據預設，這表示這些管理員 (定義為 RTCUniversalServerAdmins 群組的成員) 無法進行商務用 Skype Server 的拓撲變更。 若要授與 RTCUniversalServerAdmins 群組的成員進行拓撲變更，您必須使用 [Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) Cmdlet 指派必要的 Active Directory 許可權。
 
Test-CsSetupPermission Cmdlet 會驗證安裝商務用 Skype Server 或其元件之一所需的必要許可權是否已在指定的 Active Directory 容器上進行設定。 若未指派許可權，您可以執行 Grant-CsSetupPermission 指令指令，讓 RTCUniversalServerAdmins 群組的成員可以安裝及啟用商務用 Skype Server 的許可權。

## <a name="running-the-test"></a>執行測試

若要判斷是否為 Active Directory 容器指派安裝程式許可權，請致電 Test-CsSetupPermission Cmdlet。 指定要檢查之容器的辨別名稱。 例如，此命令會驗證容器 ou = CsServers，dc = litwareinc，dc = com 的設定許可權：

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

如需詳細資訊，請參閱 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的 [說明] 主題。

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 Test-CsSetupPermission 判斷已經在 Active Directory 容器上設定必要的許可權，則 Cmdlet 會傳回值 True：

對 

如果未設定許可權，Test-CsSetupPermission 會傳回值 False。 請注意，此值通常會包含在許多警告訊息中。 例如：

警告：存取控制專案 (ACE) atl-cs-001\RTCUniversalServerAdmins;供ExtendedRight;全全1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告：物件 "CN = 電腦，DC = litwareinc，DC=com" 的存取控制專案 (Ace) 尚未就緒。 

錯 

警告： "Test-CsSetupPermission" 處理已完成，但有警告。 在此執行期間，記錄了 "2" 個警告。 

警告：您可以在「C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html」找到詳細的結果。 

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

雖然很少例外，但如果 Test-CsSetupPermission 失敗通常表示未指派指定之 Active Directory 容器的設定許可權。 您可以使用 Grant-CsSetupPermission Cmdlet 指派這些許可權。 例如，此命令會授與網域 litwareinc.com 中電腦容器的設定許可權：

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

如需詳細資訊，請參閱 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的 [說明] 主題。