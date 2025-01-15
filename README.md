- Use dnSpy
- Update these:

Approach 1:

```
// in ticktick_WPF.Models.UserModel
proEndDate=>new DateTime?(new DateTime(2030, 12, 25));
pro=>true;
```

Approach 2:

```c#
// in ticktick_WPF.Resource.LocalSettings

public bool IsPro
{
  get
  {
    return this.SettingsModel.IsPro;
  }
  set
  {
    this.SettingsModel.IsPro = true; //force it to true
    this.OnPropertyChanged("IsPro");
  }
}

// ticktick_WPF.Dal.UserDao
//public static bool IsPro()
//{
//  return true; // force to true
//}
```
