---
title: '商務用 Skype Server 2019 的虛擬化支援 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：瞭解商務用 Skype Server 2019 的虛擬化支援。
ms.openlocfilehash: 61b54a7e2d8fc170fe63137f637246f56dcce2a01dc7af0b41ea6dc5c5c56099
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334555"
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

Windows Server 2016 和 Windows server 2019 支援 SfB Server 2019。

針對協力廠商虛擬機器管理器，您需要已超過伺服器虛擬化驗證方案的虛擬機器監控程式， (SVVP) 測試相關作業系統。

- 請參閱 SVVP 清單中的 [ [Windows Server 2016 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25)]。
- 請參閱 SVVP 清單中的[Windows Server 2019 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)。

## <a name="stress-and-performance-tool"></a>壓力和效能工具

商務用 Skype Server 2019 的壓力和效能工具組含的工具可簡化商務用 Skype Server 2019 的容量規劃。 商務用 Skype Server 2019 的壓力和效能工具可協助您：

- 簡化商務用 Skype Server 2019 的硬體規劃
- 為您提供更多有關效能調整的知識和最佳作法
- 衡量預定商務用 Skype Server 2019 部署的效能
 
您可以從 [這裡](https://www.microsoft.com/download/details.aspx?id=101447)下載工具。
