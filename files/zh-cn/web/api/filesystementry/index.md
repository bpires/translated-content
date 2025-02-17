---
title: FileSystemEntry
slug: Web/API/FileSystemEntry
---
{{APIRef("File System API")}} {{non-standard_header}}

The **`FileSystemEntry`** interface of the File and Directory Entries API represents a single in a file system. The entry can be a file or a directory (directories are represented by the {{domxref("DirectoryEntry")}} interface). It includes methods for working with files—including copying, moving, removing, and reading files—as well as information about a file it points to—including the file name and its path from the root to the entry.

> **备注：** Because this is a non-standard API, whose specification is not currently on a standards track, it's important to keep in mind that not all browsers implement it, and those that do may implement only small portions of it. Check the [Browser compatibility](#browser_compatibility) section for details.

## Basic concepts

You don't create `FileSystemEntry` objects directly. Instead, you will receive an object based on this interface through other APIs. This interface serves as a base class for the {{domxref("FileSystemFileEntry")}} and {{domxref("FileSystemDirectoryEntry")}} interfaces, which provide features specific to file system entries representing files and directories, respectively.

The `FileSystemEntry` interface includes methods that you would expect for manipulating files and directories, but it also includes a convenient method for obtaining the URL of the entry: [`toURL()`](#toURL). It also introduces a new URL scheme: `filesystem:`.

You can use the `filesystem:` scheme on Google Chrome to see all the files and folders that are stored in the origin of your app. Just use `filesystem:` scheme for the root directory of the origin of the app. For example, if your app is in [`http://www.html5rocks.com`](http://www.html5rocks.com), open` filesystem:http://www.html5rocks.com/temporary/` in a tab. Chrome shows a read-only list of all the files and folders stored the origin of your app.

### Example

To see an example of how `toURL()` works, see the [method description](#toURL). The snippet below shows you how you can remove a file by name.

```js
// Taking care of the browser-specific prefixes.
window.requestFileSystem  = window.requestFileSystem || window.webkitRequestFileSystem;

...

// Opening a file system with temporary storage
window.requestFileSystem(TEMPORARY, 1024*1024 /*1MB*/, function(fs) {
  fs.root.getFile('log.txt', {}, function(fileEntry) {

    fileEntry.remove(function() {
      console.log('File removed.');
    }, onError);

  }, onError);
}, onError);
```

## Properties

_This interface provides the following properties._

- {{domxref("FileSystemEntry.filesystem", "filesystem")}} {{ReadOnlyInline}}
  - : A {{domxref("FileSystem")}} object representing the file system in which the entry is located.
- {{domxref("FileSystemEntry.fullPath", "fullPath")}} {{ReadOnlyInline}}
  - : A {{domxref("USVString")}} object which provides the full, absolute path from the file system's root to the entry; it can also be thought of as a path which is relative to the root directory, prepended with a "/" character.
- {{domxref("FileSystemEntry.isDirectory", "isDirectory")}} {{ReadOnlyInline}}
  - : A {{jsxref("Boolean")}} which is `true` if the entry represents a directory; otherwise, it's `false`.
- {{domxref("FileSystemEntry.isFile", "isFile")}} {{ReadOnlyInline}}
  - : A Boolean which is `true` if the entry represents a file. If it's not a file, this value is `false`.
- {{domxref("FileSystemEntry.name", "name")}} {{ReadOnlyInline}}
  - : A {{domxref("USVString")}} containing the name of the entry (the final part of the path, after the last "/" character).

## Methods

_This interface defines the following methods._

- {{domxref("FileSystemEntry.copyTo", "copyTo()")}}
  - : Copies the file or directory to a new location on the file system.
- {{domxref("FileSystemEntry.getMetadata", "getMetadata()")}}
  - : Obtains metadata about the file, such as its modification date and size.
- {{domxref("FileSystemEntry.getParent", "getParent()")}}
  - : Returns a {{domxref("FileSystemDirectoryEntry")}} representing the entry's parent directory.
- {{domxref("FileSystemEntry.moveTo", "moveTo()")}}
  - : Moves the file or directory to a new location on the file system, or renames the file or directory.
- {{domxref("FileSystemEntry.remove", "remove()")}}
  - : Removes the specified file or directory. You can only remove directories which are empty.
- {{domxref("FileSystemEntry.toURL", "toURL()")}}
  - : Creates and returns a URL which identifies the entry. This URL uses the URL scheme `"filesystem:"`.

## Specifications

{{Specifications}}

This API has no official W3C or WHATWG specification.

## Browser compatibility

{{Compat("api.FileSystemEntry")}}

## See also

- [File and Directory Entries API](/zh-CN/docs/Web/API/File_and_Directory_Entries_API)
- [Introduction to the File System API](/zh-CN/docs/Web/API/File_and_Directory_Entries_API/Introduction)
- {{domxref("FileSystemFileEntry")}} and {{domxref("FileSystemDirectoryEntry")}} are based on `FileSystemEntry`.
