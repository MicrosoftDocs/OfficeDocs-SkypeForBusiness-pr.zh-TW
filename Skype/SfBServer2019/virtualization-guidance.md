---
title: '商務用 Skype Server 2019 的虛擬化支援 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：瞭解商務用 Skype Server 2019 的虛擬化支援。
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565952"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的虛擬化支援

虛擬化支援商務用 Skype Server 2019。

支援虛擬化時，需要記住一些要點：

- 維護虛擬 CPU 與實體 CPU 的1:1 比率。
- 請勿移動來賓伺服器的運作方式。
- 不支援即時系統和虛擬機器的便攜性遷移。
- 停用所有主機上的超執行緒。
- 請勿在主伺服器上設定動態記憶體。
- 使用固定磁片或傳遞磁片（而非動態磁碟）。
- 針對虛擬來賓所需的虛擬機器監控程式，允許超過6-10% 的負載。

## <a name="supported-hypervisors"></a>支援的虛擬機器監控程式

Windows Server 2016 和 Windows Server 2019 支援 SfB Server 2019。

針對協力廠商虛擬機器管理器，您需要已超過伺服器虛擬化驗證方案（SVVP）測試（適用于相關作業系統）的虛擬機器監控程式。

- 請參閱 SVVP 清單中的[Windows Server 2016 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25)。
- 請參閱 SVVP 清單中的[Windows Server 2019 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)。
