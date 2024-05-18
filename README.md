wow this is relaly old classes no jni
```cpp
class DictionaryEntry
{
public:
    DWORD64 hash;
    uintptr_t _next;
    jvm::InstanceKlass* klass;
    uintptr_t class_loader;
public:
    
    DictionaryEntry* next()
    {
        return (DictionaryEntry*)(_next & 0xFFFFFFFFFFFFFFFE);
    }
};
 
class Dictionary
{
public:
    int table_size;
    jvm::DictionaryEntry** entries;
    PVOID free_list;
    PVOID first_free_entry;
    PVOID end_block;
    int entry_size;
    int number_of_entries;
};
