---
title: 在商務用 Skype Server 中測試管理員拓朴許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如何在商務用 Skype Server 中測試拓撲許可權
ms.openlocfilehash: d70809ba929c4f1934adce2bd3c60b261bd30d71
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188500"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>在商務用 Skype Server 中測試管理員拓朴許可權

| | |
|--|--|
|驗證排程|開始進行商務用 Skype Server 部署之後。 如有許可權相關問題, 請視需要進行。|
|測試控管|Windows PowerShell|
|需要許可權|使用商務用 Skype Server Management Shell 在本機執行時, 使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。<br/><br/>使用 Windows PowerShell 的遠端實例執行時, 必須為使用者指派具有執行 CsSetupPermission Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單, 請從 Windows PowerShell 提示執行下列命令:<br/><br/>CsAdminRole \|物件 {$ _。Cmdlet-符合 "Test-CsSetupPermission"}|
|||

## <a name="description"></a>說明

根據預設, 只有網域系統管理員可以啟用商務用 Skype 伺服器拓撲, 並對商務用 Skype 伺服器基礎結構進行較大的變更。 只要您的網域管理員與您的商務用 Skype Server 管理員都是相同的, 就不會發生問題。 在許多組織中, 商務用 Skype Server 系統管理員不會在整個網域中保留系統管理許可權。 根據預設, 這表示這些系統管理員 (定義為 RTCUniversalServerAdmins 群組的成員) 無法進行商務用 Skype Server 拓撲的變更。 若要賦予 RTCUniversalServerAdmins 群組的成員對拓撲進行變更的權利, 您必須使用[Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) Cmdlet 來指派所需的 Active Directory 許可權。
 
CsSetupPermission Cmdlet 會驗證安裝商務用 Skype Server 或其中一個元件所需的許可權是否已在指定的 Active Directory 容器上設定。 如果沒有指派許可權, 您可以執行授與 CsSetupPermission Cmdlet, 將 RTCUniversalServerAdmins 群組的成員授與安裝及啟用商務用 Skype Server 的權利。

## <a name="running-the-test"></a>執行測試

若要判斷是否已指派 Active Directory 容器的設定許可權, 請呼叫 CsSetupPermission Cmdlet。 指定要檢查之容器的辨識名稱。 例如, 這個命令會驗證容器 ou = CsServers、dc = litwareinc、dc = com 的設定許可權:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

如需詳細資訊, 請參閱[Test CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果測試 CsSetupPermission 決定已在 Active Directory 容器上設定所需的許可權, 則 Cmdlet 會傳回值 True:

滿足 

如果沒有設定許可權, 測試 CsSetupPermission 會傳回值 False。 請注意, 這個值通常會括在許多警告訊息中。 例如：

警告: 存取控制專案 (ACE) atl-cs-001\RTCUniversalServerAdmins;允許ExtendedRight;所有所有1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告: 物件「CN = 電腦、DC = litwareinc、DC = com」上的存取控制專案 (Ace) 尚未就緒。 

虛假 

警告: 「Test CsSetupPermission」處理已完成, 但出現警告。 此執行期間錄製了 "2" 個警告。 

警告: 您可以在「C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html」找到詳細的結果。 

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

雖然不常見的例外狀況, 但如果測試 CsSetupPermission 失敗, 通常表示沒有為指定的 Active Directory 容器指派設定許可權。 您可以使用 Grant CsSetupPermission Cmdlet 來指派這些許可權。 例如, 這個命令會在網域 litwareinc.com 中授與電腦容器的設定許可權:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

如需詳細資訊, 請參閱[Test CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。
