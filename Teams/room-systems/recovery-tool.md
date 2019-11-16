---
title: 使用 Microsoft 團隊會議室恢復工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: 本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具]，讓您用來將已過期的系統變成受支援的狀態。
ms.openlocfilehash: bc35dc744dac5f04d537f023e790bc89c2c649d0
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675347"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft 團隊會議室恢復工具
 
本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具]，讓您用來將已過期的系統變成受支援的狀態。 當 Microsoft [團隊聊天室] 主控台顯示「系統組態已過期」錯誤時，您可以使用這個工具。
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>先決條件

下載最新的[Microsoft 團隊聊天室安裝套件](https://go.microsoft.com/fwlink/?linkid=851168)，並將其解壓縮至 Microsoft 團隊聊天室裝置可存取的 USB 記憶棒或網路共用。

您可能也需要安裝[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>驗證 Windows 版本 

1. 若要登入管理員帳戶，請移至 [**設定]> Windows 設定]> 管理員**從 Microsoft 團隊聊天室裝置登入。 此選項會將您帶到 [登入] 畫面。
2. `admin`使用密碼`sfb`登入管理員帳戶（預設系統管理員帳戶）。
3. 按一下 [開始] 功能表，然後`winver.exe`在搜尋方塊中輸入 [**執行] 命令*，並在結果上按一下。
4. 記下 [資訊] 窗格第二行的「版本」後面的數位。

>[!NOTE]
>如果顯示的版本是1607或更舊版本，請先依照在<a href="#Windows-up">恢復步驟之前更新 Windows</a>中的步驟操作，然後再 Proceding 到<a href="#Perform">執行損毀修復</a>步驟。 如果顯示的版本大於1607，請依照<a href="#Perform">執行恢復</a>中的步驟進行。

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>在恢復之前更新 Windows （如有需要）

1. 在仍以系統管理員使用者身分登入的情況下，啟動提升許可權的 Powershell 提示。
2. 執行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。
3. 請執行 Windows Update 並安裝 Windows 1709 更新。
4. 在1709更新完成之後，請重新登入管理員帳戶並安裝[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。 更新可能是從連結或使用 Windows Update 完成。
5. 如果您選用的是選擇性步驟，請安裝 [Windows Update] 中提供的任何其他更新。

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>執行恢復

1. 在 Microsoft 團隊聊天室裝置上登入系統管理員帳戶，然後啟動提升的命令提示字元。
2. 從 microsoft 團隊聊天室裝置驗證您可以存取`RecoveryTool.ps1`檔案的 Microsoft 團隊聊天室裝置，該檔案會包含在從 Microsoft 小組聊天室安裝套件提取的檔案中。 您可以在使用網路共用或 USB 磁片磁碟機上的 [準備必備元件] 中找到套件。
3. 執行 Powershell 命令`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。
4. 當腳本選取選項`1:"Repair System"`提示時。
5. 完成後，請重新開機 Microsoft 團隊聊天室裝置。 它會自動重新開機，並在第二次完全復原。



<a name="See"> </a>  
## <a name="see-also"></a>另請參閱
 
[Microsoft 團隊聊天室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)
